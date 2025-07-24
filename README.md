# Project Specification

## Requirements

### Functional

Application's domain and purpose are arbitrary.

#### CDN? FEM?

Netflix full-stack clone is suitable in terms of requirements, but maybe a little bit too big?

I guess a good start could be a small CDN with:

- User registration, login and subscription
- Content delivery leveraging geographical proximity and edge caching strategies

### Non-Functional

#### Components

The project has to include:

- At least **3 service providers**
- At least **2 service prosumers**
- At least **1 client application**

The project has to use both **REST and SOAP** services, and the interaction among these and the client application should be brokered by an **API Gateway**.

#### Interactions

With respect to the **interactions**, the following requirements should be respected.

- The **client** application should interact with at least one **prosumer** service, leveraging **three** different types of interactions
- The **client** application should also be able to interact with the **provider** services when **needed**
- The **prosumer** services should interact with at least **two** service **providers**

- At least **one asynchronous service** should be included
- At least **two prosumer** services should **cooperate concurrently**, i.e. run in parallel and synchronize to return an aggregated output
- Services should support **load balanced interactions**

#### Development

The project should be developed using the technologies seen throughout the lectures. Notably:

- **Apache Maven**
- **Docker**
- **Spring**

The project structure should be captured using **Maven Archetypes**, and each service should **support** deployment in **multiple instances**.

#### Documentation

The **purpose** of the application, with its **expected behavior** should be clearly documented with a **textual** description.

In particular, application's structure and behavior should be illustrated using the following well-known UML Diagrams.

- **Component Diagram**
- **Use Case Diagram**
- **Sequence Diagram**

Additionally, source code and services should be properly described using respectively **verbose comments** and **specifications**.

Finally, a **README** file should be provided to explain all the steps to be followed to **setup** the application.

## Notes

Particular attention has to be paid in applying correctly:

- **SOA Engineering Principles**
- **SOA Best Practices**
