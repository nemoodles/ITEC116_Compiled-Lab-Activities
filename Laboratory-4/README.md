**Laboratory Activity 4: Advanced API Implementation**

This FastAPI application allows users to manage "tasks" using an API. It supports creating, reading, updating, and deleting tasks while requiring an API key for security.

**Setup & Security**
Loads an API key from a .env file.
Checks if the user provides the correct API key in their request headers.

**Task Database**
Uses a simple in-memory list (task_db) to store tasks.
Each task has an ID, title, description, and completion status.

**CRUD Operations (Create, Read, Update, Delete)**
GET /v1/file/{task_id} → Get a task by ID.
POST /v1/file → Create a new task.
PATCH /v1/file/{task_id} → Update a task.
DELETE /v1/file/{task_id} → Remove a task.

**Two API Versions**
Version 1 (/v1) and Version 2 (/v2) are identical.
This demonstrates how APIs can evolve over time.
