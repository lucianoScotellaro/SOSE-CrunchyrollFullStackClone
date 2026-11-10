# Implementation discussion

This documents presents all the technical details related to components setup and implementation. It is intended as a structured step-by-step guide to implement all the components presented during the [architecture discussion](../system-architecture/). 

The discussion is going to address projects' subsystems in the following order:

1. Streaming Subsystem

For each subsystem a section for each component will be presented, covering the whole implementation process.

## Streaming Subsystem

### Ingestion Pipeline

The ingestion pipeline is realized based on its functional requirements, explained in the [dedicated theoretical section](../../theory/README.md#ingestion-pipeline), and its [proposed architecture](../system-architecture/README.md#ingestion-pipeline) presented in the system architecture discussion.

This section will present its implementation details by discussing the realization of each component singularly. The discussion is going to go deep into how each technology is installed and configured, and how the desired functioning is obtained.

The components will be discussed in the following order:

1. Workflow orchestrator
2. Staging storage
3. Receiver
4. Validator
5. Transformer
6. Writer

_N.B. The discussion order choice is based on the possibility to perform incremental tests throughout the implementation process of the pipeline, ensuring that each component works as intended before proceeding to the next one. For this reason each component discussion will be followed by a test section explaining how the overall functioning is tested._

#### Workflow orchestrator

Let's start with the workflow orchestrator functioning implementation then. This implementation requires **three main steps**:

1. **Orchestrator installation** within the system
2. **Definition** of the **workflow** implementing the pipeline functioning
3. **Configuration** of the workflow **automatic startup**

##### Workflow orchestrator installation

The installation of the chosen workflow orchestrator, [Argo Workflows](https://argo-workflows.readthedocs.io/en/latest/), within the system, requires **two operations**:

1. **Creation** of a [**Kubernetes**](https://kubernetes.io/docs/home/) **cluster**, that will be needed to handle all the containers of the system and, specifically in the ingestion pipeline, to allow Argo Workflows to request the scheduling of all the containers required for the workflows.
2. **Installation** of **Argo Workflows** within the cluster, that will be needed to monitor the running workflows and request the scheduling of required containers when needed.

_N.B. As just mentioned, the cluster created above will handle ALL the containers running in the system, it will not be limited to handling only the ingestion pipeline._

The **creation** of a Kubernetes **cluster** is performed into **two** different **steps**:

1. **Installation** of a Kubernetes cluster **creation tool** (e.g. [Minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download))
2. **Creation** of the Kubernetes cluster **using** a **dedicated command** in the tool (e.g. `minikube start`)

The **installation** of **Argo Workflow**, on the other hand, involves **applying** a specific **manifest** to a particular **namespace** in the **cluster**. The application of such manifest is executed by running the following commands.

1. `kubectl create namespace argo`
2. `kubectl apply --server-side -n argo -f "https://github.com/argoproj/argo-workflows/releases/download/$env:ARGO_WORKFLOWS_VERSION/quick-start-minimal.yaml"`

_N.B. To run the second command in the provided form it is needed to pass the desired Argo Workflow version as environment variable. Note also that the specific manifest used here is not suitable for production. For eventual production purposes we would use a more secure manifest, with better access control and authentication._

By **applying** the **manifest** to the argo namespace the **Argo Workflows components** are **created** within the cluster, allowing the execution and the monitoring of our workflows.

##### Ingestion workflow definition

As for the definition of the ingestion workflow, it is performed by **writing** a **yaml** file **containing** a set of [**argo templates**](https://argo-workflows.readthedocs.io/en/latest/workflow-concepts/#workflow-spec). In particular, to implement the ingestion operations, we use four different templates divided as follows:

1. Three [**template definitions**](https://argo-workflows.readthedocs.io/en/latest/workflow-concepts/#template-definitions) to **define** the **operations** and the containers to be run.
2. One [**template invocator**](https://argo-workflows.readthedocs.io/en/latest/workflow-concepts/#template-invocators) to **define** the **sequencing** of such operations.

In addition to these templates implementing the ingestion operations, an additional template is defined in the workflow to handle the staging cleanup when the workflow completes, either with success or failure.

The yaml file containing the complete workflow definition is available [here](../../src/streaming-subsystem/ingestion-pipeline/ingestion-workflow.yaml).

_N.B. Note that the operations sequencing is implemented using a steps template that runs validation, transformation, and writing in series. In addition note that each operation has two possible retries since this value is set as template default._

##### Configuration of automatic startup

The configuration of the automatic workflow startup when a master is uploaded is handled using Argo Events.

##### Testing: workflow orchestrator

Since the testing of the automatic workflow startup when a new master gets uploaded requires the staging storage to be implemented, the testing of this mechanism will be carried out during the discussion of the next component.

For now the testing is limited to controlling that the workflow orchestrator is correctly installed and working. To do this we perform the installation as mentioned above and submit an hello-world workflow to check it runs successfully.

To submit and run the hello-world workflow we proceed as follows:

1. 
2. 

#### Staging storage

