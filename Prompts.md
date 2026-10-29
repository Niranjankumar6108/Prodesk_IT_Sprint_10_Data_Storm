# Sprint 10 — AI Prompts and Development Notes

## Project

Blog REST API using Node.js, Express.js, MongoDB Atlas, and Mongoose.

## Objective

Build a RESTful Blog API with persistent MongoDB storage, complete CRUD operations, user references, Mongoose population, and a recent-posts endpoint.

## Prompt 1: Project Setup

**Prompt:**

Help me create a beginner-friendly Node.js and Express.js Blog API project using a separate project folder. Explain the folder structure and the commands required to install Express, Mongoose, dotenv, and Nodemon.

**Purpose:**

Set up the project independently and install the required dependencies.

## Prompt 2: MongoDB Atlas Connection

**Prompt:**

Show me how to connect my Express application to MongoDB Atlas using Mongoose. Store the MongoDB connection string in a `.env` file, use `process.env.MONGO_URI`, and explain how to keep database credentials out of GitHub.

**Purpose:**

Configure a secure database connection and support persistent data storage.

## Prompt 3: Post Model

**Prompt:**

Create a Mongoose Post model with title, content, author, authorId, createdAt, and updatedAt fields. Make title and content required, trim text fields, and reference a User model through authorId.

**Purpose:**

Define the blog post schema and establish a relationship between posts and users.

## Prompt 4: CRUD API Routes

**Prompt:**

Implement Express routes for creating, retrieving, updating, and deleting blog posts using Mongoose methods such as Post.create(), Post.find(), Post.findById(), Post.findByIdAndUpdate(), and Post.findByIdAndDelete(). Include appropriate input validation and error handling.

**Purpose:**

Implement database-backed CRUD operations.

## Prompt 5: User Model and Routes

**Prompt:**

Create a Mongoose User model with name and email fields. Add a POST /users endpoint that creates a user and returns the created document.

**Purpose:**

Store author information separately and support references from blog posts.

## Prompt 6: Populate Author Information

**Prompt:**

Explain how to use Mongoose `.populate()` to retrieve the name and email of the author referenced by a post's authorId field. Help me test the relationship between the User and Post collections.

**Purpose:**

Return related author details when retrieving posts.

## Prompt 7: Three Most Recent Posts

**Prompt:**

Create a GET /posts/recent/top endpoint that returns up to three most recent blog posts. Sort by createdAt in descending order, limit the result to three documents, and populate the author's name and email.

**Purpose:**

Implement a recent-posts endpoint using MongoDB sorting and limiting.

## Prompt 8: Local API Testing

**Prompt:**

I do not have Postman installed. Show me how to test POST, GET, PUT, and DELETE endpoints using Windows PowerShell and Invoke-RestMethod. Explain how to capture a user ID and pass it as authorId when creating a post.

**Purpose:**

Test API endpoints directly from PowerShell without installing an additional API client.

## Prompt 9: Troubleshooting

**Prompt:**

Help me troubleshoot MongoDB ObjectId references, incorrect authorId values, Mongoose populate results, and Express route errors. Explain the fixes step by step for a beginner.

**Purpose:**

Diagnose errors and verify that related documents are returned correctly.

## Prompt 10: Documentation and Deployment

**Prompt:**

Help me prepare a README.md and Prompts.md for my MongoDB Blog API project. Include installation instructions, environment variables, API endpoints, example requests, testing notes, and deployment steps for Render. Never include real database credentials.

**Purpose:**

Document the project and prepare it for GitHub submission and deployment.

## Development Notes

- The Sprint 10 project is maintained separately from the Sprint 9 project.
- MongoDB Atlas connectivity was confirmed in the local server logs.
- User creation, post creation, retrieval, update, and deletion were tested using PowerShell.
- The author reference and `.populate()` behavior were verified for a post created with a valid user ID.
- The three-most-recent-posts endpoint was tested locally.
- The project should be deployed only after confirming the final files and environment configuration.

## Security Notes

- Keep `.env` out of version control.
- Use placeholders in documentation instead of real database credentials.
- Configure production environment variables through the hosting provider.
- Never commit passwords, access tokens, or database connection strings.