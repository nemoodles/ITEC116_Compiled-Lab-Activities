**Laboratory Activity 3: Working with JSON**

**short description**
- This activity demonstrates how to integrate an external API (`jsonplaceholder.typicode.com`) into a FastAPI application. The program retrieves and formats data from external APIs and presents it in a structured manner.
  
**objective of the activity**
- Learn how to fetch data from an external API using Python’s `requests` module.
- Understand how to process and manipulate JSON responses.
- Develop new API endpoints that interact with multiple APIs.
- Return structured JSON responses.

**How to run the code**
1. Ensure you have Python installed (version 3.7+ recommended).
2. Install the required dependencies:  "```sh
   pip install fastapi uvicorn requests"
3. Save the provided Python script as main.py.
4. Run the FastAPI server: **uvicorn main:app --reload**
5. Open your browser and navigate to the FastAPI interactive docs: "http://127.0.0.1:8000/docs"
6. Use tools like **Postman, cURL**, or the interactive docs to test the API endpoints.

**Expected output**

**GET /posts/ (Retrieve All Posts)**

**Request:**

GET http://127.0.0.1:8000/posts/

**Response:**

[
  {
    "userId": 1,
    "id": 1,
    "title": "Sample Title",
    "body": "This is a sample post body."
  }
]

**GET /comments/?postId=1 (Retrieve Comments for a Specific Post)**

**Request:**

GET http://127.0.0.1:8000/comments/?postId=1

**Response:**

[
  {
    "postId": 1,
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com",
    "body": "This is a comment."
  }
]

**GET /formatted_posts/{userID} (Retrieve Formatted Posts by a User)**

**Request:**

GET http://127.0.0.1:8000/formatted_posts/1

**Response:**

{
  "userID": 1,
  "posts": [
    {
      "post_title": "Sample Title",
      "post_body": "This is a sample post body."
    }
  ]
}

**GET /detailed_post/{userID} (Retrieve All Posts and Comments by a User)**

**Request:**

GET http://127.0.0.1:8000/detailed_post/1

**Response:**

{
  "userID": 1,
  "posts": [
    {
      "post_title": "Sample Title",
      "post_body": "This is a sample post body.",
      "comments": [
        {
          "commenter_email": "johndoe@example.com",
          "commenter_name": "John Doe",
          "comment": "This is a comment."
        }
      ]
    }
  ]
}


