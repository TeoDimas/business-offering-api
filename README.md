# Business Offering API

A Spring Boot microservice for managing service offerings within the Location Management System, specifically handling offerings related to offices and ATMs. Provides RESTful APIs to create, update, retrieve, and delete service offerings to ensure efficient management of services available at various locations.

---

## Overview

Business Offering API is a modular Spring Boot application designed to manage service offerings associated with location entities such as offices and ATMs. It functions as a key component of the Location Management System microservices ecosystem and features:

- Persistence of service offerings with descriptive and eligibility details  
- RESTful API for offering CRUD operations  
- Clean separation of concerns with entity, model, service, repository, and controller layers  
- DTO-entity mapping using custom converters  
- H2 database support for development and testing  
- Integration-ready design to work alongside Location API and other microservices  
- Swagger UI for interactive API documentation  

---

## Features

- Full CRUD operations for service offerings  
- Entity-to-DTO and DTO-to-entity mapping for clean API boundaries  
- Service layer abstraction for business logic and repository interaction  
- Spring Data JPA repository integration  
- REST controllers exposing API endpoints with proper HTTP response management  
- Comprehensive unit and integration testing recommended  
- API documentation via Swagger UI for easy exploration and testing  

---

## Technology Stack

- Java 11  
- Spring Boot 3.x  
- Maven 3.x  
- Spring Data JPA  
- H2 Database (file-based)  
- Lombok for boilerplate code reduction  
- SLF4J & Logback for logging  
- Swagger UI for API documentation  

---

## Getting Started

### Prerequisites

- Java JDK 11 or higher  
- Maven 3.x  
- IDE like IntelliJ IDEA or Eclipse for development/debugging  
- Optional: Running Location API microservice for integration testing  

### Installation

1. Clone the repository:

```bash
git clone https://github.com/yourorg/business-offering-api.git
cd business-offering-api
```
### 2. Build the Project

```bash
mvn clean install
```

### 3. Run the Application

```bash
mvn spring-boot:run
```

### 4. Access the API

Open your browser or API client and navigate to:  
`http://localhost:8080/api/v1`

# H2 Database Console
spring.h2.console.enabled=true
spring.datasource.url=jdbc:h2:file:~/h2/offeringdb
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update

# Logging
logging.config=classpath:logback-spring.xml

# Swagger UI
springdoc.api-docs.enabled=true
springdoc.swagger-ui.enabled=true

## API Endpoints

| Method | Endpoint                 | Description                                   |
|--------|--------------------------|-----------------------------------------------|
| GET    | `/api/v1/offerings`      | Retrieve all service offerings                |
| GET    | `/api/v1/offerings/{id}` | Retrieve a service offering by ID             |
| POST   | `/api/v1/offerings`      | Create a new service offering                 |
| PUT    | `/api/v1/offerings/{id}` | Update an existing service offering (planned) |
| DELETE | `/api/v1/offerings/{id}` | Delete a service offering (planned)           |

## Architecture Overview

- **Spring Boot** microservice with layered architecture:
  - **Controller Layer**: REST API endpoints
  - **Service Layer**: Business logic and data transformation
  - **Repository Layer**: Database access with Spring Data JPA
  - **Entity & Model Layer**: JPA entities and DTO models
- Clean conversion between entities and DTOs via custom converters
- Designed to integrate with Location API for location-offering relationship management

---

## Testing

- Use **Postman**, **Swagger UI**, or any REST client to test the endpoints.
- Typical test flows include:
  - Creating new service offerings
  - Fetching all offerings or a specific offering by ID
  - Validating error handling and response codes

---

## Development & Debugging

- Developed with Java 11 and Maven 3 for build management
- Debugging supported via IDEs like IntelliJ IDEA
- Log output configured with SLF4J and Logback for easier troubleshooting

---

## Logging & Monitoring

- Logs include info, debug, and error levels for API operations and database interactions
- Configuration located in `logback-spring.xml` for centralized control

---

## API Documentation

- Integrated **Swagger UI** available at:  
  `http://localhost:8080/swagger-ui.html` or `http://localhost:8080/swagger-ui/index.html`
- Provides interactive documentation of all API endpoints with request/response models
- Supports direct API testing via web interface

---

## Microservice Ecosystem Integration

- Business Offering API works alongside the Location API to provide a comprehensive location and service management system.
- Designed to consume and provide data to other microservices via RESTful APIs.
- Encourages modular development and deployment of microservices within the Location Management System.


