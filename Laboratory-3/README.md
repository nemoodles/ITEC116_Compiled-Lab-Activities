**This FastAPI application interacts with an external API to retrieve and manipulate posts and comments data. 
The goal is to learn how to fetch API data, format it, and build new API endpoints using Python.**

**Fetching Data from an External API**
The requests library is used to fetch posts and comments from jsonplaceholders.
The json module helps convert API responses into Python-friendly data.

**Basic API Endpoints**
/posts/ → Retrieves all posts or a specific post using a query parameter (postId).
/comments/ → Retrieves all comments or comments for a specific post using a query parameter (postId).

**Formatting API Data**
/formatted_posts/{userID} → Filters posts by userID and returns only the title and body.
/formatted_comment/{postID} → Fetches comments for a given post and organizes them neatly with commenter_name, email, and comment.

**Creating a New API Endpoint (/detailed_post/{userID})**
Retrieves all posts from a specific user.
For each post, it fetches all related comments.
Returns structured data, combining posts with their respective comments.

**Step by step process on how this code works**

1. The API first fetches all posts.
2. It filters out only those that match the given userID.
3. For each post, it calls another API to fetch the comments related to that post.
4. It organizes the data into a structured JSON response.
