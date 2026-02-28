# Crunchyroll Full-Stack Clone

## Introduction

Crunchyroll Full-Stack Clone is an application developed as end-of-course project for the course of **Service-Oriented Software Engineering**.

The project was developed based on the reported [assignment](./assignment.pdf). Since the domain and the purpose of the application were arbitrary, the idea was to experiment with an **over-the-top video on-demand system**. The goal was therefore to build a well-engineered system capable of storing and delivering video content.

The choice was mainly driven by the required **microservices** architectural style, that perfectly meets the most relevant [**non-functional requirements**](./docs/requirements.md/#non-functional) of such a system. Notably: **performance**, **scalability** and **availability**.

Below are reported:

- Project's [setup](#setup), to locally run the application
- Project's [main features](#systems-main-features)

A deeper look into system's [**requirements**](./docs/requirements.md) and [**architecture**](./docs/system-architecture/) is provided through the [**docs**](./docs/) folder, while a discussion of all the **implementation details** is available in the [**services**](./services/) folder.

## Setup

## System's Main Features

### Components Independence

Provided:

- On the architectural level by building the system as composition of black box components, publishing required and provided interfaces.
- On the implementation level by the use of containerization and publish-subscribe

This ensures great extensibility and maintainability.

Essendo questo il progetto finale per un corso di service-oriented software engineering non si può non nominare come prima caratteristica fondamentale del sistema la costruzione di quest'ultimo come composizione di servizi indipendenti e distribuiti.

### Components Standardization

By the use of a Maven Archetype, it provides all the developers with the same project structure, providing higher readability and easier management for the project codebase.
