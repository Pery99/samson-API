# API Documentation

## Base URL
```
http://localhost:3000/api
```

## Authentication Endpoints

### Register User
```http
POST /auth/register
```

### Login User
```http
POST /auth/login
```

### Get User Profile
```http
GET /auth/me
```
**Required:** Authentication token in headers
**Response:**
```json
{
  "_id": "user_id",
  "fullname": "User's Full Name",
  "email": "user@example.com",
}
```

## Protected Routes

### Get Protected Data
```http
GET /protected
```
**Required:** Authentication token in headers

## General Endpoints

### Health Check
```http
GET /
```
Returns a simple "Working" message to confirm the API is running.

## Authentication
The API uses JWT tokens for authentication. Include the token in the Authorization header:
```
Authorization: Bearer <your_token>
```

## Error Responses
```json
{
  "error": "Error message description"
}
```

## Environment Variables
The following environment variables are required:
- `PORT`: Server port (default: 3000)
- `MONGODB_URI`: MongoDB connection string
- `JWT_SECRET`: Secret key for JWT token generation

## CORS
The API is configured to accept requests from:
- http://localhost:5173
