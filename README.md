# API Interaction and Data Formatting

This project demonstrates how to work with external APIs, manipulate their data using Python, and create a custom API with FastAPI. 

### Endpoints

#### 1. **Get All Posts or a Specific Post**
- **GET** `/posts/`
  - Query Parameter: `postId` (optional)
  - Returns all posts or a specific post based on the query parameter.

#### 2. **Get All Comments or Comments by Post ID**
- **GET** `/comments/`
  - Query Parameter: `postId` (optional)
  - Returns all comments or comments for a specific post.

#### 3. **Formatted Posts by User ID**
- **GET** `/formatted_posts/{userID}`
  - Path Parameter: `userID` (required)
  - Returns posts for the given user, formatted as:
    ```json
    {
        "userID": <userID>,
        "posts": [
            {
                "post_title": "...",
                "post_body": "..."
            }
        ]
    }
    ```

#### 4. **Formatted Comments by Post ID**
- **GET** `/formatted_comment/{postID}`
  - Path Parameter: `postID` (required)
  - Returns comments for the given post, formatted as:
    ```json
    {
        "post_id": <postID>,
        "comments": [
            {
                "commenter_email": "...",
                "commenter_name": "...",
                "comment": "..."
            }
        ]
    }
    ```

#### 5. **Detailed Posts and Comments by User ID**
- **GET** `/detailed_post/{userID}`
  - Path Parameter: `userID` (required)
  - Returns all posts of a user along with comments for each post, formatted as:
    ```json
    {
        "userID": <userID>,
        "posts": [
            {
                "post_title": "...",
                "post_body": "...",
                "comments": [
                    {
                        "commenter_name": "...",
                        "commenter_email": "...",
                        "comment_body": "..."
                    }
                ]
            }
        ]
    }
    ```

## Installation

1. Clone this repository or download the code.
2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

## Running the API

Start the FastAPI server locally:
```bash
uvicorn main:app --reload
```

The API will be available at `http://127.0.0.1:8000`.

## Testing the API

- Open a browser or API testing tool like Postman.
- Use the provided endpoints to interact with the API and view the JSON responses.

## Notes

- This project uses the [JSONPlaceholder API](https://jsonplaceholder.typicode.com/) for demonstration purposes.
- The `requests` library is used to make HTTP calls to the external API.
- The project showcases how to manipulate JSON data into custom formats and integrate it into new APIs.

## Contributions
Contributions are welcome! Feel free to submit issues or pull requests if you have improvements or suggestions.
