# NoBroker Clone: Broker-Free Real Estate Platform

A full-stack real estate platform that connects property owners directly with tenants, with no broker in between. Owners can list properties, tenants can search and send inquiries, and access is secured with role-based authentication.

Built as a **team project of 4 members** during training at Mountblue Technologies.

![Java](https://img.shields.io/badge/Java-ED8B00?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?logo=springboot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![CircleCI](https://img.shields.io/badge/CircleCI-343434?logo=circleci&logoColor=white)

## Features

- **Property listing:** owners can create, update and manage their property listings
- **Search:** tenants can search and filter available properties (query performance improved by about 60%)
- **Direct inquiries:** tenants contact owners directly through the platform
- **Secure auth:** role-based authentication and authorization using JWT and OAuth2 with Spring Security
- **CI/CD:** automated build, test and Docker deployment pipeline on CircleCI

## Tech Stack

| Layer | Technologies |
|---|---|
| Backend | Java, Spring Boot, Spring Data JPA, Hibernate, Spring Security |
| Authentication | OAuth2, JWT |
| Database | MySQL |
| Frontend | HTML, CSS, JavaScript |
| Build and Testing | Maven, JUnit, embedded Tomcat |
| DevOps | Docker, CircleCI |

## Team and Contributions

| Member |
|---|---|
| Rajat Kumar ([@rajatkcs94](https://github.com/rajatkcs94))
| Pakkurthi Chandu
| Kankipati Vakdevi 
| viswanath yandapalli

> Original repository: [PakkurthiChandu/nobroker-application](https://github.com/PakkurthiChandu/nobroker-application)

## Architecture

```
JavaScript Frontend  -->  Spring Boot REST API  -->  MySQL
                           |- Spring Security (JWT / OAuth2)
                           |- Spring Data JPA / Hibernate
```

## Getting Started

### Prerequisites

- Java 17 (or the version your project uses)
- Maven 3.8+
- MySQL 8+
- Docker (optional)

### 1. Clone the repository

```bash
git clone https://github.com/rajatkcs94/nobroker-application.git
cd nobroker-application
```

### 2. Configure the database

Create a MySQL database and update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/nobroker
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```

Add your JWT secret and OAuth2 client credentials as environment variables rather than committing them.

### 3. Run the backend

```bash
mvn clean install
mvn spring-boot:run
```

The API starts on `http://localhost:8080` (embedded Tomcat).

### 4. Open the frontend

The frontend is built with HTML, CSS and JavaScript. Once the backend is running, open `http://localhost:8080` in your browser.

> If your frontend lives in a separate folder instead of being served by Spring Boot, open `frontend/index.html` in a browser (or serve it with a tool like `npx serve frontend`) and point the API base URL in your JS config to `http://localhost:8080`.

### Run with Docker (optional)

```bash
docker build -t nobroker-app .
docker run -p 8080:8080 nobroker-app
```

## Running Tests

```bash
mvn test
```

## CI/CD

The CircleCI pipeline runs on every push: it builds with Maven, runs the JUnit tests, and builds the Docker image.

## API Overview

| Method | Endpoint | Description | Access |
|---|---|---|---|
| POST | `/api/auth/register` | Register a new user | Public |
| POST | `/api/auth/login` | Log in and receive a JWT | Public |
| GET | `/api/properties` | Search and list properties | Public |
| POST | `/api/properties` | Create a listing | Owner |
| POST | `/api/inquiries` | Send an inquiry to an owner | Tenant |


## Screenshots


## Future Improvements

- Image upload for property listings
- Saved searches and favorites
- In-app chat between owners and tenants

## License

_Add a license, e.g. MIT._
