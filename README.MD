# Sprint 10 — Blog API with MongoDB Atlas

## Project Overview

This project is a RESTful Blog API built using Node.js, Express.js, MongoDB Atlas, and Mongoose. It demonstrates NoSQL database integration, CRUD operations, user references, document population, and retrieving the three most recent blog posts.

The API stores blog posts and user information in MongoDB Atlas, allowing data to persist beyond server restarts.

## Technologies Used

- Node.js
- Express.js
- MongoDB Atlas
- Mongoose
- dotenv
- JavaScript
- PowerShell for API testing

## Features

- Create, read, update, and delete blog posts.
- Create users and store their information in MongoDB.
- Associate posts with users using MongoDB ObjectId references.
- Populate author details using Mongoose `.populate()`.
- Retrieve the three most recent posts.
- Validate post IDs and required fields.
- Store database credentials securely using environment variables.
- Persist data in MongoDB Atlas.

## Project Structure

```text
sprint10-blog-api/
├── src/
│   ├── models/
│   │   ├── Post.js
│   │   └── User.js
│   ├── routes/
│   │   ├── posts.js
│   │   └── users.js
│   ├── middleware/
│   └── server.js
├── .env
├── .env.example
├── .gitignore
├── package.json
├── package-lock.json
├── README.md
└── Prompts.md
```

Note: The structure above describes the intended project organization. Keep only the files and folders that actually exist in your project.

## Installation

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd sprint10-blog-api
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL.

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the project root:

```env
PORT=5000
MONGO_URI=your_mongodb_atlas_connection_string
```

Replace the placeholder with your MongoDB Atlas connection string.

**Security:** Never commit your `.env` file or expose your database credentials.

### 4. Start the Application

For development:

```bash
npm run dev
```

For production:

```bash
npm start
```

The local API runs at:

`http://localhost:5000`

## API Endpoints

### General

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | API health check, if configured |

### Users

| Method | Endpoint | Description |
|---|---|---|
| POST | `/users` | Create a user |

### Posts

| Method | Endpoint | Description |
|---|---|---|
| POST | `/posts` | Create a post |
| GET | `/posts` | Retrieve all posts |
| GET | `/posts/:id` | Retrieve a post by ID |
| PUT | `/posts/:id` | Update a post |
| DELETE | `/posts/:id` | Delete a post |
| GET | `/posts/recent/top` | Retrieve the three most recent posts |

## Example Requests

### Create a User

**POST** `/users`

```json
{
  "name": "Niranjan Kumar",
  "email": "niranjan.sprint10@example.com"
}
```

### Create a Post

**POST** `/posts`

```json
{
  "title": "My First MongoDB Post",
  "content": "This post is stored persistently in MongoDB Atlas.",
  "author": "Niranjan Kumar",
  "authorId": "REPLACE_WITH_USER_OBJECT_ID"
}
```

Replace `REPLACE_WITH_USER_OBJECT_ID` with the `_id` returned by the user creation endpoint.

### Update a Post

**PUT** `/posts/:id`

```json
{
  "title": "Updated MongoDB Post",
  "content": "The post has been updated successfully."
}
```

### Retrieve the Three Most Recent Posts

**GET** `/posts/recent/top`

This endpoint sorts posts by creation time in descending order and returns up to three posts.

## Database Design

### User Model

Stores user information such as:

- `name`
- `email`
- `createdAt`
- `updatedAt`

### Post Model

Stores blog post information such as:

- `title`
- `content`
- `author`
- `authorId`
- `createdAt`
- `updatedAt`

The `authorId` field references a User document using a MongoDB ObjectId. Mongoose `.populate()` retrieves the associated author's selected fields.

## Testing

The API was tested locally using Windows PowerShell and `Invoke-RestMethod`.

The following operations were successfully tested:

- Creating users and posts.
- Retrieving all posts.
- Retrieving a post by ID.
- Updating a post.
- Deleting a post.
- Retrieving the three most recent posts.
- Populating author information for linked posts.

MongoDB Atlas connectivity was also confirmed through the application startup logs.

## Deployment

The application can be deployed to Render.

1. Push the project to GitHub.
2. Create a Web Service on Render and connect the repository.
3. Set the build command to `npm install`.
4. Set the start command to `npm start`.
5. Add `MONGO_URI` and any other required environment variables in the Render dashboard.
6. Confirm that the deployed service can connect to MongoDB Atlas.

Configure MongoDB Atlas network access appropriately for the deployed service.

## Project Links

- **GitHub Repository:** Add your repository URL here.
- **Live API:** Add your deployed Render URL here.
- **Demo Video:** Add your demonstration video URL here.

## Learning Outcomes

This project demonstrates practical experience with REST API development, MongoDB Atlas, Mongoose schemas, CRUD operations, ObjectId references, document population, environment configuration, and API testing.

## Author

Niranjan Kumar

Sprint 10 — NoSQL Cloud Databases & Object Data Modeling