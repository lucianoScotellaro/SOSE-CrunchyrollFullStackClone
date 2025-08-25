# Crunchyroll Full-Stack Clone

## Introduction

Crunchyroll Full-Stack Clone is an application developed as end-of-course project for the course of **Service-Oriented Software Engineering**.

Since the domain and the purpose of the application were arbitrary, the idea was to experiment with an over-the-top video on-demand system, leveraging a content-delivery network for better performance.

Below are reported:

- Project's [requirements](#requirements)
- Project's [setup](#setup) to locally run the application
- Project's [main features](#systems-main-features)

## Requirements

### Functional

Given the chosen domain and purpose, the project should comply with the following functional requirements.

_Note: all the functional requirements are expressed as user stories._

#### User

- As a user I want to **register**, **login** and **subscribe** to the platform so that I can access its functionalities
- As a user I want to **browse** application's **catalog** so that I can search for video content to watch
- As a user I want to **play** video content so that I can watch it
- As a user I want to **pause**, **rollback** and **fast-forward** videos so that I freely move through the video content

#### Manager

- As a manager I want to upload video content to the platform so that it is accessible to users
- As a manager I want to remove video content from the platform so that it is no more accessible to users

### Non-Functional

The following non-functional requirements are extracted from the [assignment's description](./assignment.pdf).

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

#### Note

Particular attention has to be paid in applying correctly:

- **SOA Engineering Principles**
- **SOA Best Practices**

<p style="color:red;">Aggiungi descrizione di quali sono i SOA Principles le Best Practices</p>

#### Domain-specific Requirements

Below are reported all the non-functional requirements that have been added based on the specific application-domain.

- Content should be delivered using multiple servers, leveraging geographical proximity and edge caching strategies, to improve delivery performance

## Setup

## System's Main Features
