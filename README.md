# CARMATE — Secure Car Service Platform

A systems analysis and design project for a security-focused marketplace that connects customers requesting vehicle services with service providers who can submit quotes, accept bookings, complete jobs, and receive payments.

> **Project scope:** CARMATE was developed as a team systems-analysis and design project. This repository documents the platform requirements, data model, process design, and security architecture. Technologies discussed as implementation options are not presented as deployed components unless supported by implementation evidence.

## Problem

Finding and coordinating vehicle service can involve fragmented communication, unclear pricing, limited quote comparison, and disconnected booking and payment workflows.

CARMATE was designed to bring the service lifecycle into one platform:

**Request → Quote → Compare → Book → Service → Pay → Review**

## Core Actors

### Customer
- Creates a vehicle service request
- Provides service details and location information
- Receives and compares provider quotes
- Selects a provider and books service
- Completes payment
- Leaves a review

### Service Provider
- Reviews available service requests
- Submits quotes with pricing and estimated arrival/service information
- Manages accepted jobs
- Updates job progress

### Administrator
- Supports platform oversight
- Manages administrative workflows and platform integrity

## Core Processes

The system was organized into six primary process areas:

| Process | Purpose |
| --- | --- |
| P1 — Post Request | Capture a customer's service request |
| P2 — Manage Quotes | Allow providers to respond with service quotes |
| P3 — Match & Book | Connect a customer with the selected provider |
| P4 — Payment | Track payment authorization and completion states |
| P5 — Notifications | Deliver workflow and status notifications |
| P6 — Reviews & Administration | Capture reviews and support administrative oversight |

## Data Model

CARMATE's logical data design includes seven principal data stores:

| Data Store | Key Information |
| --- | --- |
| Users | Accounts, roles, contact information, ratings |
| Service Requests | Category, description, location, budget, request status |
| Quotes | Provider, amount, ETA, message, quote status |
| Jobs | Provider assignment, schedule, job status |
| Payments | Amount, payment method, transaction status |
| Reviews | Rating, comments, creation time |
| Notifications | User notifications, type, payload, read status |

See [Data Model](docs/data-model.md) for a more detailed logical schema.

## Security by Design

Security was considered as part of the architecture rather than as an afterthought.

The design addresses:

- authentication and identity management,
- role-based authorization for customers, providers, and administrators,
- protection of data in transit and at rest,
- secure payment boundaries,
- validation and safe handling of uploaded files,
- administrative access protection,
- API authorization,
- auditability and security-relevant logging,
- separation of responsibilities between application components.

See [Security Architecture](docs/security-architecture.md).

## System Design

The platform was decomposed around the flow of information between users, application processes, and persistent data stores. This approach helped define system boundaries before selecting implementation technologies.

Key design considerations included:

- REST-style application interfaces,
- relational data modeling,
- authentication/token-based session design,
- cloud deployment options,
- caching,
- containerization,
- web application firewall protection.

These represent **architecture considerations and technology options**, not a claim that every component was deployed.

## My Contribution

As part of the project team, my work contributed to the analysis and design of the CARMATE platform, including requirements, process/data-flow modeling, database/data-dictionary design, architecture discussions, and security considerations.

This repository focuses on the technical design artifacts and security thinking developed through the project.

## Documentation

- [System Architecture](docs/system-architecture.md)
- [Data Model](docs/data-model.md)
- [Security Architecture](docs/security-architecture.md)

## Skills Demonstrated

**Systems Analysis & Design** · **Security Architecture** · **Data Modeling** · **Requirements Analysis** · **Access Control Design** · **Secure Application Design** · **Database Design** · **Technical Documentation**

## Team Project

CARMATE originated as a collaborative university project and was originally developed under the working name **ESTIM8R**. The portfolio name CARMATE is used here for clearer product presentation.

This repository documents the project without representing team work as an individual production deployment.
