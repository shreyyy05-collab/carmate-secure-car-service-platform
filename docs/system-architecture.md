# System Architecture

CARMATE was designed as a multi-role service marketplace with customers, providers, and administrators interacting with application services backed by persistent data stores.

## Logical Flow

```text
Customer / Provider / Admin
            |
            v
      Application Layer
            |
   -----------------------
   |    |    |    |     |
Requests Quotes Jobs Payments Notifications
            |
            v
       Data Storage
```

## Application Responsibilities

The application layer coordinates:

1. account and role management,
2. service-request creation,
3. provider quote submission,
4. quote comparison and selection,
5. job lifecycle management,
6. payment-state tracking,
7. notifications,
8. reviews and administrative workflows.

## Technology Evaluation

During architecture planning, multiple implementation approaches were considered, including:

- backend frameworks from the Node.js, Django, Spring, and .NET ecosystems,
- REST or GraphQL interfaces,
- relational and document-oriented database options,
- caching technologies such as Redis,
- major cloud platforms,
- Docker/container deployment,
- web application firewall options,
- managed or custom authentication solutions,
- OAuth 2.0/JWT-based identity patterns.

These were evaluated as architecture choices. Listing them here does **not** mean every technology was implemented in the project.

## Design Goal

The architecture separates user-facing workflows from persistent data and security responsibilities so that authentication, authorization, payment boundaries, data protection, and administrative controls can be reasoned about explicitly.
