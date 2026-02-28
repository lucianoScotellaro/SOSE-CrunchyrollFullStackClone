# System Architecture

## Static Description

### Subsystem View

Given the [domain-specific functional and non-functional requirements](./requirements.md/#domain-specific-requirements), Crunchyroll Full-Stack Clone high-level **architecture** has been designed as **composition** of the following **four** **subsystems**, each addressing specific well-defined concerns.

1. **User Subsystem**: responsible for all the operations related to the **user**. From registration and login, to recommendations, and watchlists.
2. **Content Subsystem**: responsible for all the operations related to **video content**. Mainly storage, delivery, upload, and removal.
3. **Billing Subsystem**: responsible for all the operations related to **payments**. Notably subscriptions, and bills management.
4. **Monitoring Subsystem**: responsible for all the operations related to system **observability**. These include logging system behavior, in addition to monitoring utilization, and status of each single component (Kafka with real-time data visualization).

The choice to build the system as a composition of units as independent as possible, has been made based on **two** **considerations**.

1. It keeps the high-level **architecture** simple, and so more **readable**.
2. It allows **independent** **development** and **maintenance** of single units.

### API Gateway

In addition to the subsystems mentioned above, the architecture also includes an API Gateway. It is used to **abstract** all the **backend** components from the client point-of-view by providing a single access-point. This increases system **security** and allows **load balancing**.

### Box and Line Diagram

A complete overview of the **high-level architecture** described so far is presented by the following **box and line** diagram.

![subsystem-view](./system-architecture/static-description/subsystem-view.png)

### Low-Level Architecture: from Subsystems to Components

Starting from the subsystems defined before, further refinements have been performed, leading to the definition of the following services in each subsystem.

### Component Diagram

### Users Interactions: Use-Case Diagram

## Dynamic Description

### Behavior: Sequence Diagrams
