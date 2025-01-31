
**Laboratory Activity 5: Deploying API in Cloud**

**short description**
- This activity involves deploying the API developed in Laboratory Activity 4 to the cloud platform Render. The API manages a to-do list with versioning (apiv1 and apiv2) and requires an API key for access.
  
**objective of the activity**
- Develop and deploy an API to a cloud platform (Render).
- Ensure the deployed API is accessible via a public URL.

**files in the repository**
- `.env`: Stores the API key securely.  
- `.gitignore`: Excludes sensitive files from version control.  
- `lab4.py`: The main FastAPI application that provides task management functionality.
  
**How to run the code**
You can run the codes same as laboratory 4, the only difference is that you upload this code on render.

### Step 1: Prepare Your Code
1. Ensure your code is pushed to a GitHub repository.
2. Include the following files:
   - `main.py`
   - `requirements.txt`
   - `.gitignore` (to exclude `.env`)

### Step 2: Create a Render Account
1. Sign up for a free account at [Render](https://render.com/).
2. Verify your email address.

### Step 3: Deploy to Render
1. Go to the **Dashboard** and click **New +** > **Web Service**.
2. Connect your GitHub repository.
3. Configure the deployment:
   - **Name**: `itec116_<surname>` (replace `<surname>` with your actual surname).
   - **Region**: Choose the closest region.
   - **Branch**: Select the branch containing your code.
   - **Runtime**: Python 3.
   - **Build Command**: `pip install -r requirements.txt`.
   - **Start Command**: `uvicorn main:app --host 0.0.0.0 --port 10000`.
4. Add environment variables:
   - Go to the **Environment** section.
   - Add the following variable:
     - Key: `LAB4_API_KEY`
     - Value: `RawrBarney` (use the same API key as in your code).
5. Click **Create Web Service** to deploy.

### Step 4: Access Your Deployed API
1. Once the deployment is complete, Render will provide a public URL for your API.
2. Copy the Base URL from the Render dashboard (e.g., https://itec116-surname.onrender.com).
3. Test your API using a browser, Postman, or cURL
   - GET https://itec116-surname.onrender.com/v1/file/1
   - X-API-KEY: secretkey
4. Visit https://itec116-surname.onrender.com/docs to access the interactive Swagger UI for testing.

### Step 5: Verify and Submit Your Deployment
1. Ensure your API is working by testing all endpoints.
2. Submit the deployed API URL (e.g., https://itec116-surname.onrender.com) along with your GitHub repository URL.

**API Endpoints**

### Version 1 (`apiv1`)
- **GET /apiv1/database/{task_id}**: Retrieve a task by its ID.
- **POST /apiv1/database**: Create a new task.
- **PATCH /apiv1/database/{task_id}**: Update an existing task.
- **DELETE /apiv1/database/{task_id}**: Delete a task by its ID.

### Version 2 (`apiv2`)
- **GET /apiv2/database/{task_id}**: Retrieve a task by its ID.
- **POST /apiv2/database**: Create a new task.
- **PATCH /apiv2/database/{task_id}**: Update an existing task.
- **DELETE /apiv2/database/{task_id}**: Delete a task by its ID.

### General Endpoints
- **GET /**: Welcome message.
- **GET /health**: Health check endpoint.
