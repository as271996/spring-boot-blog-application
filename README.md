# Spring Boot Blog Application

A full-stack blog management application built using Java, Spring Boot, Spring MVC, Thymeleaf, Spring Data JPA, Spring Security, and PostgreSQL.

The application allows users to create and manage blog posts, organize posts using tags, add comments, search and filter content, and schedule posts for future publication.

## Features

### Blog Posts
- Create, view, update, and delete blog posts
- Automatically generate excerpts from post content
- Schedule posts for future publication
- Track created, updated, and published timestamps
- Associate multiple tags with a post

### Comments
- Add comments to blog posts
- Update and delete comments
- Associate comments with individual posts

### Search, Sort & Filtering
- Search posts by title, content, author, and tags
- Sort posts by author and publication date
- Sort in ascending or descending order
- Filter posts by author, tag, and publication date range

### Pagination
- Paginated blog listing
- Displays posts page by page with Previous/Next navigation

### Authentication
- User authentication using Spring Security
- Authenticated users can create and manage blog posts

## Tech Stack

**Language:** Java 8  
**Frameworks:** Spring Boot, Spring MVC, Spring Security, Spring Data JPA  
**Frontend:** Thymeleaf, HTML, Bootstrap  
**Database:** PostgreSQL  
**ORM:** Hibernate / JPA  
**Build Tool:** Maven

## Architecture

The application follows a layered Spring Boot architecture:

```text
Controller
   ↓
Service
   ↓
Repository
   ↓
PostgreSQL
```

The code is organized into separate layers for request handling, business logic, persistence, security configuration, and domain entities.

## Project Structure

```text
src/
├── main/
│   ├── java/
│   │   └── com/mountblue/blog/blogapplication/
│   │       ├── config/
│   │       ├── controller/
│   │       ├── DAO/
│   │       ├── entity/
│   │       └── service/
│   │
│   └── resources/
│       ├── templates/
│       └── application.properties
│
└── test/
```

## Data Model

The application uses four main persistent entities:

### Posts
Stores blog post information such as:
- title
- excerpt
- content
- author
- publication status
- publication timestamp
- created and updated timestamps

A post can have multiple comments and multiple tags.

### Comments
Stores comments associated with blog posts:
- name
- email
- comment
- post ID
- created and updated timestamps

### Tags
Stores tags associated with blog posts.

Posts and tags use a many-to-many relationship through the `post_tags` table.

### Users
Stores application users used for authentication:
- name
- email
- password

## Running the Application Locally

### Prerequisites

Make sure the following are installed:

- Java 8
- PostgreSQL
- Git

Maven installation is optional because the project includes the Maven Wrapper.

### 1. Clone the Repository

```bash
git clone https://github.com/as271996/Blogapplication.git
cd Blogapplication
```

### 2. Create the PostgreSQL Database

Create a PostgreSQL database named:

```text
Blog_Application
```

For example:

```sql
CREATE DATABASE Blog_Application;
```

### 3. Configure Database Credentials

Update `src/main/resources/application.properties` with your PostgreSQL configuration:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/Blog_Application
spring.datasource.username=your_username
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
```

### 4. Run the Application

On macOS/Linux:

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

### 5. Open the Application

Once the application starts, open:

```text
http://localhost:8080/blog/bloglist
```

## Future Improvements

This project can be further improved by adding:

- BCrypt password hashing for secure credential storage
- Role-based authorization
- REST API support
- DTO and validation layers
- Global exception handling
- Database migrations using Flyway or Liquibase
- Dockerized application and PostgreSQL setup
- Unit and integration tests
- CI/CD using GitHub Actions
- API documentation using OpenAPI / Swagger
- Upgrade to a newer Java and Spring Boot version

## Author

**Amit Singh**

Senior Backend Engineer with experience in distributed systems, system design, microservices, scalability, and reliability.

- GitHub: [github.com/as271996](https://github.com/as271996)
- LinkedIn: [linkedin.com/in/amit-singh-sp27](https://www.linkedin.com/in/amit-singh-sp27)
