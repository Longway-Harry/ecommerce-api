# Talabat Commerce Platform

> Backend-focused enterprise commerce infrastructure built with ASP.NET Core 8, Onion Architecture, Redis caching, JWT authentication, Stripe payments, and operationally maintainable service boundaries.

A production-oriented e-commerce platform engineered with strong separation of concerns, scalable service abstractions, and infrastructure-first architectural discipline.

This repository represents the type of backend/system engineering work suitable for long-term SaaS and operational software environments — emphasizing maintainability, extensibility, and infrastructure clarity rather than tutorial-style CRUD development.

---

# Engineering Positioning

This project aligns closely with a backend-focused engineering profile centered around:

- scalable SaaS infrastructure
- maintainable enterprise architecture
- operational tooling
- API-driven systems
- payment and identity workflows
- infrastructure separation
- long-term maintainability
- production-oriented backend engineering

The architecture and implementation style intentionally prioritize:

- low coupling
- clean dependency direction
- explicit service boundaries
- reusable query composition
- infrastructure abstraction
- operational reliability
- backend extensibility

---

# Solution Overview

The solution is built using a multi-project Onion Architecture approach.

It contains:

- RESTful E-Commerce API
- Admin MVC Dashboard
- Shared service/infrastructure layers
- JWT authentication system
- Redis basket caching
- Stripe payment integration
- Specification-based querying
- Generic repository + unit of work patterns
- Result-pattern service orchestration

The project demonstrates how a modern commerce platform can be structured for long-term growth instead of short-term feature delivery.

---

# Architecture

```text
Talabat Commerce Solution
│
├── Domain
│   ├── Entities
│   ├── Contracts
│   └── Core abstractions
│
├── Service
│   ├── Business logic
│   ├── Specifications
│   ├── Mapping profiles
│   └── Service orchestration
│
├── ServiceAbstraction
│   └── Dependency inversion contracts
│
├── Presistance
│   ├── EF Core
│   ├── Repositories
│   ├── Identity context
│   ├── Seeding
│   └── Unit of Work
│
├── Presentation
│   ├── API controllers
│   ├── Filters
│   └── HTTP response layer
│
├── Web
│   ├── Application startup
│   ├── Middleware
│   ├── Dependency registration
│   └── Configuration
│
├── Admin.Dashboard
│   ├── MVC controllers
│   ├── Views
│   └── Administrative workflows
│
└── Shared
    ├── DTOs
    ├── Query parameters
    └── Common response contracts
```

---

# Core Architectural Characteristics

## Onion Architecture

Dependencies always point inward.

The Domain layer remains isolated from:

- Entity Framework
- ASP.NET Core
- Redis
- Stripe
- Infrastructure concerns

This enables:

- long-term maintainability
- testability
- easier refactoring
- infrastructure replacement
- cleaner scaling paths

---

## Specification Pattern

The project avoids scattering query logic across controllers.

Instead, reusable specifications encapsulate:

- filtering
- sorting
- pagination
- eager loading
- query composition

Examples include:

- product filtering
- category queries
- order retrieval
- search workflows

This creates significantly cleaner business logic boundaries.

---

## Generic Repository + Unit of Work

Data access is abstracted through:

- generic repositories
- aggregate coordination
- transactional consistency

This keeps business logic independent from direct EF Core implementation details.

---

## Result Pattern

The service layer avoids exception-driven flow control.

Instead, operations return explicit result objects representing:

- success
- validation failure
- domain failure
- infrastructure failure

This produces:

- predictable service contracts
- cleaner API responses
- easier debugging
- more maintainable orchestration

---

## Redis Basket Infrastructure

Basket/cart state is stored in Redis.

The caching implementation is architected as reusable infrastructure instead of ad-hoc endpoint logic.

Benefits:

- lower database pressure
- faster cart retrieval
- stateless API scalability
- operational efficiency

---

## Payment Integration

Stripe payment lifecycle handling includes:

- PaymentIntent creation
- payment updates
- succeeded payment handling
- order synchronization
- payment state management

The implementation demonstrates real-world payment orchestration concerns instead of simplified mock flows.

---

# Technology Stack

| Category | Technology |
|---|---|
| Backend Framework | ASP.NET Core 8 |
| API Style | RESTful API |
| ORM | Entity Framework Core |
| Database | SQL Server |
| Authentication | JWT + ASP.NET Identity |
| Dashboard Authentication | Cookie Authentication |
| Caching | Redis |
| Payment Provider | Stripe |
| Mapping | AutoMapper |
| Documentation | Swagger / OpenAPI |
| UI Layer | ASP.NET MVC + Bootstrap |
| Architecture | Onion Architecture |

---

# Major Features

## E-Commerce API

- Product catalog
- Product filtering
- Pagination
- Sorting
- Category management
- Brand management
- Basket/cart management
- Order processing
- Payment workflows
- JWT authentication
- Identity management
- Error handling middleware
- Redis-backed basket persistence
- Swagger documentation

---

## Admin Dashboard

The solution also includes a dedicated MVC administrative dashboard.

Administrative capabilities include:

- product management
- order oversight
- operational administration
- account management
- internal workflows

The dashboard shares the same backend infrastructure and service layer as the API.

This avoids code duplication and demonstrates proper architectural reuse.

---

# Project Structure Analysis

## Strong Points

### Excellent Layer Separation

The separation between:

- domain
- infrastructure
- services
- presentation
- dashboard UI

is significantly cleaner than most tutorial-based .NET commerce projects.

---

### Production-Oriented Thinking

The project includes:

- Redis
- Stripe
- JWT auth
- multi-context databases
- specification pattern
- result pattern
- middleware orchestration

which moves it beyond basic CRUD demonstrations.

---

### Backend Engineering Focus

The strongest aspect of the repository is not UI.

It is:

- architecture discipline
- service orchestration
- infrastructure composition
- operational backend thinking

This aligns well with enterprise SaaS and long-term platform engineering.

---

### Reusable Infrastructure

Reusable abstractions are consistently applied across:

- repositories
- services
- filters
- specifications
- response handling

This demonstrates maintainability awareness.

---

# Areas That Could Be Expanded Further

Potential future improvements:

- background job processing (Hangfire / Quartz)
- distributed tracing
- structured logging (Serilog)
- OpenTelemetry instrumentation
- Dockerized local infrastructure
- CI/CD pipelines
- integration testing suite
- rate limiting
- message queue integration
- domain events
- CQRS segregation
- health checks
- Kubernetes deployment manifests

---

# Local Development

## Prerequisites

- .NET 8 SDK
- SQL Server
- Redis
- Stripe account

---

## Run the Solution

```bash
git clone <repository-url>
cd Talabat-ECommerce-Api-Project
```

Restore dependencies:

```bash
dotnet restore
```

Apply migrations:

```bash
dotnet ef database update
```

Run the API:

```bash
dotnet run --project Web
```

Run the dashboard:

```bash
dotnet run --project Admin.Dashboard
```

---

# Authentication

The API uses:

- JWT Bearer Authentication
- ASP.NET Core Identity
- role-based authorization

The dashboard uses:

- cookie authentication
- session-based administrative access

---

# Engineering Value Demonstrated

This repository demonstrates:

- scalable backend architecture
- operational API design
- maintainable infrastructure layering
- payment system integration
- infrastructure abstraction discipline
- reusable service composition
- enterprise-oriented .NET engineering practices

It is particularly suitable as a portfolio project for:

- backend engineering roles
- SaaS infrastructure teams
- enterprise .NET positions
- operational platform engineering
- long-term product companies
- European engineering environments emphasizing maintainability and architecture quality

---

# Author

Nguyễn Minh Long  
Backend-Focused Full-Stack Engineer

Specializing in:

- SaaS infrastructure
- backend architecture
- API integrations
- automation systems
- operational software
- scalable business systems

Focused on building reliable, maintainable, production-grade systems with long-term engineering value.

