# Spring Boot CRUD APIs (Categories & Products)

## 📌 Before Installation
Hi Dear,  

Before installation of this application, you need to install the below software:

1. **VS Code**  
2. **MySQL**  

⚠️ If you don’t install these, the project will not run.  

Also, you need to create a database named **`mydb`** in MySQL:

```sql
CREATE DATABASE mydb;
🚀 Developed APIs
🔹 1) Category CRUD Operations
➤ Create Category
POST http://localhost:8080/api/categories
Request:

json
Copy
Edit
{
  "name": "Electronics"
}
Response:

json
Copy
Edit
{
  "id": 1,
  "name": "Electronics"
}
➤ Get Category by ID
GET http://localhost:8080/api/categories/{id}
Example:
http://localhost:8080/api/categories/1
Response:

json
Copy
Edit
{
  "id": 1,
  "name": "Electronics"
}
➤ Get All Categories (Paginated)
GET http://localhost:8080/api/categories?page=0
Response (example):

json
Copy
Edit
{
  "content": [
    { "id": 1, "name": "Electronics" },
    { "id": 2, "name": "Sports" },
    { "id": 3, "name": "Hocky" },
    { "id": 4, "name": "cricket" },
    { "id": 5, "name": "batminton" }
  ],
  "pageable": {
    "pageNumber": 0,
    "pageSize": 5
  },
  "totalElements": 10,
  "totalPages": 2,
  "first": true,
  "last": false
}
➤ Update Category
PUT http://localhost:8080/api/categories/{id}
Example:
http://localhost:8080/api/categories/1

Request:

json
Copy
Edit
{
  "name": "Updated Electronics"
}
Response:

json
Copy
Edit
{
  "id": 1,
  "name": "Updated Electronics"
}
➤ Delete Category
DELETE http://localhost:8080/api/categories/{id}
Example:
http://localhost:8080/api/categories/1
Response:
200 OK

🔹 2) Product CRUD Operations
➤ Create Product
POST http://localhost:8080/api/products
Request:

json
Copy
Edit
{
  "name": "Samsung Galaxy s1",
  "description": "Samsung smartphone",
  "price": 1100.0,
  "category": { "id": 1 }
}
➤ Get All Products (Paginated)
GET http://localhost:8080/api/products?page=0
Response:

json
Copy
Edit
{
  "content": [
    {
      "id": 3,
      "name": "Samsung Galaxy s1",
      "price": 1100.0,
      "category": {
        "id": 2,
        "name": "Sports"
      }
    }
  ],
  "pageable": {
    "pageNumber": 0,
    "pageSize": 5
  },
  "totalElements": 1,
  "totalPages": 1,
  "first": true,
  "last": true
}
➤ Get Product by ID
GET http://localhost:8080/api/products/{id}
Example:
http://localhost:8080/api/products/3
Response:

json
Copy
Edit
{
  "id": 3,
  "name": "Samsung Galaxy s1",
  "price": 1100.0,
  "category": {
    "id": 2,
    "name": "Sports"
  }
}
➤ Update Product
PUT http://localhost:8080/api/products/{id}
Example:
http://localhost:8080/api/products/1

Request:

json
Copy
Edit
{
  "name": "iPhone 15 Pro Max",
  "description": "Updated description: iPhone 15 Pro Max with better camera",
  "price": 1399.99,
  "quantity": 40,
  "category": {
    "id": 1
  }
}
➤ Delete Product
DELETE http://localhost:8080/api/products/{id}
Example:
http://localhost:8080/api/products/1
Response:
200 OK
