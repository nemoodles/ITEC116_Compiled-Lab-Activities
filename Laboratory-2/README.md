**This FastAPI application acts as a simple user management API, allowing users to be retrieved, added, updated, and deleted. 
The API interacts with a mock database (users_db), which is just a list of dictionaries containing user details like user_id and name.**

**User Data Structure (User Class)**
Defines how a user object should be structured using BaseModel.
Each user has:
user_id (integer)
name (string)

**Retrieving Users (GET /users)**
If no user ID is provided, it returns all users.
If a user ID is given, it returns the matching user.
If the user doesn’t exist, it returns an error message.

**Creating a User (POST /users)**
Adds a new user to users_db, but only if the user_id doesn’t already exist.
If the ID is duplicate, it returns an error.
If successful, it returns a confirmation message.

**Updating a User (PUT /users/{user_id})**
Finds a user by user_id and updates their name.
If the user doesn’t exist, it returns an error message.

**Deleting a User (DELETE /users/{user_id})**
Finds and removes the user from users_db.
If successful, it returns the deleted user’s data.
If the user doesn’t exist, it returns an error message.

**Step by step process on how this code works**
**The app starts with a small mock user database.**
**Users can:**
1. Retrieved (all users or a specific user)
2. Added (with a unique user ID)
3. Updated (changing only the user’s name)
4. Deleted (removing a user by ID)
**Each request receives a structured JSON response.**
