**Laboratory Activity 4: Advanced API Implementation**

**short description**
- This activity demonstrates how to build a **Task Management API** using **FastAPI**. The API includes CRUD (Create, Read, Update, Delete) operations with authentication using an **API Key** stored in an `.env` file.
  
**objective of the activity**
- Learn how to implement **CRUD operations** in FastAPI.
- Understand how to use **environment variables** for authentication.
- Explore the use of **APIRouter** to manage API versions.
- Implement **API key verification** for secured access.

**files in the repository**
- `.env`: Stores the API key securely.  
- `.gitignore`: Excludes sensitive files from version control.  
- `lab4.py`: The main FastAPI application that provides task management functionality.
  
**How to run the code**
1. Install Dependencies
   - Ensure you have Python installed (version 3.7+ recommended). Then install the required packages: "```sh
pip install fastapi uvicorn python-dotenv "
2. Create a .env File
   - Ensure you have an .env file with the API key: **echo "LAB_API_KEY=your_secret_api_key" > .env**
3. Run the FastAPI Server
   - **uvicorn lab4:app --reload**
4. Access API Documentation
   - "http://127.0.0.1:8000/docs"

**API Endpoints**

**Version 1 (/v1/file)**

**GET**
- /v1/file/{task_id}	
   - retrieve a task by task_id
     
**POST**	
- /v1/file
   - Create a new task
     
**PATCH**	
- /v1/file/{task_id}
  - Update an existing task
  
**DELETE**	
- /v1/file/{task_id}
  - Delete a task

**Version 2 (/v2/file)**

**GET**
- /v2/file/{task_id}	
   - retrieve a task by task_id
     
**POST**	
- /v2/file
   - Create a new task
     
**PATCH**	
- /v2/file/{task_id}
  - Update an existing task
  
**DELETE**	
- /v2/file/{task_id}
  - Delete a task

**Authentication**

All API requests require an API Key in the headers: **X-API-KEY: your_secret_api_key**

**Expected output** 

**GET /v1/file/1 (Retrieve a Task)**

**Request:**

GET http://127.0.0.1:8000/v1/file/1

**Headers:**

X-API-KEY: your_secret_api_key

**Response (If Task Exists):**

{
  "message": "Task retrieved successfully.",
  "task": {
    "task_id": 1,
    "task_title": "Laboratory Activity",
    "task_desc": "Create Lab Act 2",
    "is_finished": false
  }
}

**Response (If Task Not Found):**

{
  "detail": "Task with ID 1 not found."
}

**POST /v1/file (Create a Task)**

**Request:**

POST http://127.0.0.1:8000/v1/file

**Headers:**

X-API-KEY: your_secret_api_key

**JSON Body:**

{
  "task_title": "New Task",
  "task_desc": "This is a test task",
  "is_finished": false
}

**Response:**

{
  "message": "Task successfully created.",
  "task": {
    "task_id": 2,
    "task_title": "New Task",
    "task_desc": "This is a test task",
    "is_finished": false
  }
}

**PATCH /v1/file/1 (Update a Task)**

**Request:**

PATCH http://127.0.0.1:8000/v1/file/1

**Headers:**

X-API-KEY: your_secret_api_key

**JSON Body:**

{
  "task_title": "Updated Task",
  "task_desc": "Updated description",
  "is_finished": true
}

**Response:**

{
  "message": "Task successfully updated."
}

**DELETE /v1/file/1 (Delete a Task)**

**Request:**

DELETE http://127.0.0.1:8000/v1/file/1

**Headers:**

X-API-KEY: your_secret_api_key

**Response:**

{
  "message": "Task with ID 1 successfully deleted."
}
