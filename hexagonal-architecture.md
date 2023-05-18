# Hexagonal Architecture

It is also known as **Ports** & **Adapters**.

Separates insides (domain layer which holds the business logic) and outsides (infrastructure layers).

The idea of Hexagonal Architecture is to put **inputs** and **outputs** at the edges of our design. Business logic should not depend on whether we expose a REST or a GraphQL API, and it should not depend on where we get data from — a database, a microservice API exposed via gRPC or REST, or just a simple CSV file.

## Defining the core concepts
Leveraged from the Hexagonal Architecture, the three main concepts that define our business logic are **Entities**, **Repositories**, and **Interactors**.

- **Entities** are the domain objects (e.g., a Movie or a Shooting Location) — they have no knowledge of where they’re stored (unlike Active Record in Ruby on Rails or the Java Persistence API).

- **Repositories** are the interfaces to getting entities as well as creating and changing them. They keep a list of methods that are used to communicate with data sources and return a single entity or a list of entities. (e.g. UserRepository)

- **Interactors** are classes that orchestrate and perform domain actions — think of Service Objects or Use Case Objects. They implement complex business rules and validation logic specific to a domain action (e.g., onboarding a production)

