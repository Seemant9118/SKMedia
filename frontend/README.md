# Social Media Application

This is a social media application that allows users to register, login, create, read, update, and delete posts. It uses JSON Web Tokens (JWT) for session and token management.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
  - [User](#user)
    - [Register](#register)
    - [Login](#login)
  - [Post](#post)
    - [Create a Post](#create-a-post)
    - [Read a Post](#read-a-post)
    - [Update a Post](#update-a-post)
    - [Delete a Post](#delete-a-post)

## Installation

1. Clone the repository:

```
git clone https://github.com/your-username/social-media-app.git
```

2. Change into the project directory:

```
cd social-media-app
```

3. Install the dependencies:

```
npm install
```

4. Set up the environment variables by creating a `.env` file and filling in the required information:

```
DATABASE_URL=your_database_url
JWT_SECRET=your_jwt_secret
```

5. Start the application:

```
npm start
```

## Usage

After installation and starting the application, you can interact with the social media app through the provided API endpoints. You can use a tool like [Postman](https://www.postman.com/) to make HTTP requests to the endpoints.

Make sure to include the necessary headers and include the JWT token in the request headers for authenticated endpoints.

## API Endpoints

### User

#### Register

- Endpoint: `POST /api/register`
- Description: Register a new user.
- Request Body:

```json
{
  "username": "example_user",
  "password": "password123"
}
```

- Response:

```json
{
  "message": "User registered successfully"
}
```

#### Login

- Endpoint: `POST /api/login`
- Description: Log in an existing user.
- Request Body:

```json
{
  "username": "example_user",
  "password": "password123"
}
```

- Response:

```json
{
  "message": "Login successful",
  "token": "your_jwt_token"
}
```

### Post

#### Create a Post

- Endpoint: `POST /api/posts`
- Description: Create a new post for the authenticated user.
- Request Headers:

```json
{
  "Authorization": "Bearer your_jwt_token"
}
```

- Request Body:

```json
{
  "title": "My Post",
  "content": "This is the content of my post"
}
```

- Response:

```json
{
  "message": "Post created successfully",
  "postId": "your_post_id"
}
```

#### Read a Post

- Endpoint: `GET /api/posts/:postId`
- Description: Read the details of a specific post.
- Request Headers:

```json
{
  "Authorization": "Bearer your_jwt_token"
}
```

- Response:

```json
{
  "postId": "your_post_id",
  "title": "My Post",
  "content": "This is the content of my post",
  "userId": "your_user_id",
  "createdAt": "2023-06-03T12:34:56Z",
  "updatedAt": "2023-06-03T12:34:56Z"
}
```

#### Update a Post

- Endpoint: `PUT /api/posts/:postId`
- Description: Update the content of a specific post.
- Request Headers:

```json
{
  "Authorization": "Bearer