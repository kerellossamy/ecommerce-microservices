# Ecommerce Microservices Project

This project is a learning-oriented microservices architecture built with **Spring Boot**. It consists of three independent microservices—**Users Service**, **Products Service**, and **Orders Service**—each running on its own port and sharing a single MySQL database. The parent repository uses **Git submodules** to include each service’s repository as a folder in the main project.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Tech Stack](#tech-stack)
3. [Prerequisites](#prerequisites)
4. [Cloning the Project](#cloning-the-project)

---

## Project Overview

In a real-world microservices architecture, each service is typically developed, deployed, and scaled independently. This project demonstrates:

- Three standalone Spring Boot services (users, products, orders).
- Each service exposes REST endpoints and follows a layered architecture (controller, service, repository, entity, DTO, mapper).
- The **Orders Service** calls the other two services via **`RestTemplate`** (client classes) to verify users and products before creating an order.
- All three services share a single MySQL database (`ecommerce_db`), but each service manages its own tables:
  - `users` table for user data
  - `products` table for product data
  - `orders` table for order data
- Demonstrates use of JDK 21, Maven, Lombok, MapStruct, and Git submodules.

---

## Tech Stack

- **Language:** Java 21
- **Framework:** Spring Boot
- **Build Tool:** Maven
- **ORM:** Spring Data JPA (Hibernate)
- **Database:** MySQL (single database with separate tables per service)
- **HTTP Client:** `RestTemplate` (for inter-service calls)
- **Mapping:** MapStruct
- **Dependency Injection & Boilerplate Reduction:** Lombok
- **Version Control:** Git + GitHub Submodules
- **IDE (optional):** IntelliJ IDEA, Eclipse, VS Code, etc.
- **Testing:** Postman or cURL (no frontend)

---

## Prerequisites

Before you begin, make sure you have the following installed and configured on your machine:

1. **Java 21 JDK**  
   - Download & install from [Oracle](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html) or [AdoptOpenJDK](https://adoptium.net/).
   - Verify with:
     ```bash
     java -version
     ```
     You should see something like:
     ```
     java version "21.0.1" 2023-10-17 LTS
     ```

2. **Maven (≥ 3.6.x)**  
   - Download & install from [Maven official website](https://maven.apache.org/download.cgi).
   - Verify with:
     ```bash
     mvn -version
     ```

3. **MySQL Server**  
   - Download & install MySQL Community Server (≥ 8.0).  
   - Optional GUI clients: MySQL Workbench, DBeaver, etc.

4. **Git**  
   - Download & install from [Git SCM](https://git-scm.com/downloads).  
   - Verify with:
     ```bash
     git --version
     ```

5. **Postman** (or cURL) for testing REST endpoints.

---

## Cloning the Project
**Clone the parent repository with submodules**  
   Use the `--recurse-submodules` flag to automatically fetch all submodules:
   ```bash
   git clone --recurse-submodules https://github.com/kerellossamy/ecommerce-microservices.git
   cd ecommerce-microservices


