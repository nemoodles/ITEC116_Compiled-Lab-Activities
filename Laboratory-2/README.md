**Laboratory Activity 2: Working with HTTP actions and API parameters**

**short description**
- This activity demonstrates how to create a RESTful API using FastAPI that allows users to perform **CRUD (Create, Read, Update, Delete)** operations on a user database.
  
**objective of the activity**
- Understand how to build a REST API using FastAPI.
- Learn how to use **query parameters**, **path parameters**, and **request bodies** in API endpoints.
- Implement CRUD operations for user data management.

**How to run the code**
1. Ensure you have Python installed (version 3.7+ recommended).
2. Install FastAPI and Uvicorn:
3. Save the provided Python script as **main.py**.
4. Run the FastAPI server with this code: **uvicorn main:app --reload**
5. Open your browser and navigate to the FastAPI interactive docs: "http://127.0.0.1:8000/docs"
6. Use tools like **Postman, cURL**, or the interactive docs to test the API endpoints.


**Expected output**
- GET http://127.0.0.1:8000/users
  
{
  "status": "ok",
  "result": [
    {"user_id": 1, "name": "John Doe"},
    {"user_id": 2, "name": "Jane Smith"}
  ]
}

- GET http://127.0.0.1:8000/users?user_id=1
  
**Response (If User Exists):**

{
  "status": "ok",
  "result": {"user_id": 1, "name": "John Doe"}
}

**Response (If User Not Found):**

{
  "error": "User not found"
}


**POST /users (Create a New User)**

POST http://127.0.0.1:8000/users

**JSON Body:**

{
  "user_id": 3,
  "name": "Alice Johnson"
}

**Response:**

{
  "status": "ok"
}

**Error (If User ID Already Exists):**

{
  "error": "User ID already existing"
}


**PUT /users/{user_id} (Update a User)**

**Request:**

PUT http://127.0.0.1:8000/users/1

**JSON Body:**

{
  "user_id": 1,
  "name": "Johnathan Doe"
}

**Response:**

{
  "status": "ok",
  "updated_data": {"user_id": 1, "name": "Johnathan Doe"}
}


**DELETE /users/{user_id} (Delete a User)**

**Request:**

DELETE http://127.0.0.1:8000/users/1

**Response:**

{
  "status": "ok",
  "removed_data": {"user_id": 1, "name": "John Doe"}
}

**Response (If User Not Found):**

{
  "error": "User not found. Cannot delete record"
}

