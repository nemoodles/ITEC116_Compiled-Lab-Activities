**Laboratory 1: Factorial API using FastAPI**

**short description**
This activity demonstrates how to create a simple API using FastAPI that calculates the factorial of a given number.

**objective of the activity**
- Understand how to use FastAPI for creating APIs.
- Learn how to handle dynamic URL parameters in FastAPI.
- Implement a basic algorithm to compute factorials.

**How to run the code**
1. Ensure you have Python installed (version 3.7+ recommended).
2. Install FastAPI and Uvicorn (a server for running FastAPI applications):
3. Save the provided Python script as **main.py**.
4. Run the FastAPI server with this code: **uvicorn main:application --reload**
5. Access the API using a browser "http://127.0.0.1:8000/factorial/5"
6. The API will return the factorial of the given number in JSON format.

**Dependencies**
Python 3.7+
FastAPI
Uvicorn (for running the server)

**Expected output**
If you visit "http://127.0.0.1:8000/factorial/5" the API should return:
{
  "result": 120
}

If the input is 0, it will return:
{
  "result": false
}
