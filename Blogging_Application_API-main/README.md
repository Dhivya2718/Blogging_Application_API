# 📝 Blog REST API

A modern, scalable **Blog REST API** built with **Spring Boot**, enabling users to manage posts, comments, and categories seamlessly.  
Supports JWT authentication, role-based access control, file uploads, search, sorting, pagination, and more.

![Blog API Banner](https://via.placeholder.com/1200x300.png?text=Blog+REST+API+Banner)

---

## 🌟 Features

- **Authentication & Authorization**
  - JWT-based authentication
  - Role-based access control (ADMIN, USER)
- **Posts & Comments**
  - CRUD operations for posts
  - Add/remove comments
  - Filter posts by category or author
- **Categories**
  - CRUD operations for categories
  - Retrieve posts by category
- **Search, Sort & Pagination**
  - Search by title or content
  - Sort by date, popularity, or custom fields
  - Paginate through results
- **File Uploads**
  - Upload/update post images
- **Error Handling & Responses**
  - Custom `ApiResponse<T>` class
  - Detailed exception handling
- **Database**
  - MySQL with One-to-Many and Many-to-Many relationships
- **Documentation**
  - Interactive API docs with **Swagger**

---

## 🛠️ Tech Stack

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/SpringBoot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON-web-tokens&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)

---

## ⚡ Installation

1. Clone the repository:
```bash
git clone https://github.com/YourUsername/Blogging_Application_Backend.git
cd blog-app-apis
application.properties:
spring.datasource.url=jdbc:mysql://localhost:3306/your_database
spring.datasource.username=your_username
spring.datasource.password=your_password
Run the application:
mvn spring-boot:run
http://localhost:8080/swagger-ui/index.html
| **Category**   | **Method** | **Endpoint**                                     | **Auth Required** |
| -------------- | ---------- | ------------------------------------------------ | ----------------- |
| **Auth**       | POST       | `/api/v1/auth/login`                             | No                |
|                | POST       | `/api/v1/auth/register`                          | No                |
| **Users**      | GET        | `/api/users/`                                    | No                |
|                | POST       | `/api/users/`                                    | Yes               |
|                | GET        | `/api/users/{id}`                                | No                |
|                | PUT        | `/api/users/{id}`                                | Yes               |
|                | DELETE     | `/api/users/{id}`                                | Yes (Admin)       |
| **Posts**      | GET        | `/api/posts`                                     | No                |
|                | GET        | `/api/post/{id}`                                 | No                |
|                | GET        | `/api/posts/search/{keyword}`                    | No                |
|                | POST       | `/api/user/{userId}/category/{categoryId}/posts` | Yes               |
|                | PUT        | `/api/posts/{postId}`                            | Yes               |
|                | DELETE     | `/api/posts/{postId}`                            | Yes (Admin)       |
|                | POST       | `/api/post/image/upload/{postId}`                | Yes               |
| **Categories** | GET        | `/api/categories/`                               | No                |
|                | POST       | `/api/categories/`                               | Yes               |
|                | GET        | `/api/categories/{id}`                           | No                |
|                | PUT        | `/api/categories/{id}`                           | Yes               |
|                | DELETE     | `/api/categories/{id}`                           | Yes               |
| **Comments**   | POST       | `/api/post/{id}/comments`                        | Yes               |
|                | DELETE     | `/api/comments/{id}`                             | Yes               |
