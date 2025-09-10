# Requirements

This document presents all the requirements considered during the application development, starting from the [baseline requirements](#project-baseline-requirements), extracted from the [project assignment](../assignment.pdf), leading to the [domain-specific requirements](#domain-specific-requirements), added based on the chosen application domain.

_Note: all the functional requirements are identified by a unique identifier and expressed in the form of user stories._

## Project Baseline Requirements

### Components

The project has to include:

- At least **3 service providers**
- At least **2 service prosumers**
- At least **1 client application**

The project has to use both **REST and SOAP** services, and the interaction among these and the client application should be brokered by an **API Gateway**.

### Interactions

With respect to the **interactions**, the following requirements should be respected.

- The **client** application should interact with at least one **prosumer** service, leveraging **three** different types of interactions
- The **client** application should also be able to interact with the **provider** services when **needed**
- The **prosumer** services should interact with at least **two** service **providers**

- At least **one asynchronous service** should be included
- At least **two prosumer** services should **cooperate concurrently**, i.e. run in parallel and synchronize to return an aggregated output
- Services should support **load balanced interactions**

### Development

The project should be developed using the technologies seen throughout the lectures. Notably:

- **Apache Maven**
- **Docker**
- **Spring**

The project structure should be captured using **Maven Archetypes**, and each service should **support** deployment in **multiple instances**.

### Documentation

The **purpose** of the application, with its **expected behavior** should be clearly documented with a **textual** description.

In particular, application's structure and behavior should be illustrated using the following well-known UML Diagrams.

- **Component Diagram**
- **Use Case Diagram**
- **Sequence Diagram**

Additionally, source code and services should be properly described using **verbose comments** and **specifications**.

Finally, a **README** file should be provided to explain all the steps to be followed to **setup** the application.

### Note

Particular attention has to be paid to correctly applying:

- **SOA Engineering Principles**
- **SOA Best Practices**

<p style="color:red;">Aggiungi descrizione di quali sono i SOA Principles e le Best Practices</p>

## Domain-Specific Requirements

### Functional

#### User

- **US1**: As a user I want to **register**, **login** and **subscribe** to the platform so that I can access its functionalities
- **US2**: As a user I want to **browse** application's **catalog** so that I can search for video content to watch
- **US3**: As a user I want to **play** video content so that I can watch it
- **US4**: As a user I want to **pause**, **rollback** and **fast-forward** videos so that I can freely move through the video content

#### Manager

- **US5**: As a manager I want to **upload** video content to the platform so that it is accessible to users
- **US6**: As a manager I want to **remove** video content from the platform so that it is no more accessible to users

### Non-Functional

- **Security**: The system should only provide **manager access** to **authorized personnel**, to ensure that video content is uploaded exclusively by them. In addition, it has to **store** and **deliver** video content **securely**, to guarantee adequate protection against data breaches and data sniffing attacks.
- **Performance**: The system should provide **low-latency** video content browsing and **delivery**, offering the user a real-time experience.
- **Scalability**: The system should be able to scale, both **horizontally** and **vertically**, to accommodate increasing numbers of users and video contents.
- **Availability**: The system should provide **zero-downtime** **failure** management and **updates**, to ensure that it is always available.
- **Reliability**: The system should {testing}, {observability => logs}
- **Maintainability**: The system should be easily updatable, both in terms of features and technologies, {componenti indipendenti e modulari in modo da poter essere aggiornati, sostituiti e aggiunti all'occorrenza}.
- **Usability**: The system should provide a **simple** and clear user interface, along with a **intuitive** and smooth **user experience**, to offer easy browsing and playback of video content.
