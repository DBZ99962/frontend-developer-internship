# API Documentation

## Base URL
`http://localhost:5000/api` or `https://your-deployment-url.com/api`

## Authentication
All protected endpoints require JWT token in Authorization header:
```
Authorization: Bearer <jwt_token>
```

## Auth Endpoints

### Signup
**POST** `/auth/signup`
```json
Request:
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123"
}

Response (201):
{
  "message": "User created successfully",
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Login
**POST** `/auth/login`
```json
Request:
{
  "email": "john@example.com",
  "password": "securePassword123"
}

Response (200):
{
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Get Profile
**GET** `/auth/profile` (Protected)
```json
Response (200):
{
  "_id": "507f1f77bcf86cd799439011",
  "name": "John Doe",
  "email": "john@example.com",
  "createdAt": "2025-12-12T10:30:00Z"
}
```

## Task Endpoints

### Get All Tasks
**GET** `/tasks` (Protected)
```json
Response (200):
[
  {
    "_id": "507f1f77bcf86cd799439012",
    "title": "Complete Project",
    "description": "Finish the frontend assignment",
    "completed": false,
    "createdAt": "2025-12-12T10:30:00Z"
  }
]
```

### Create Task
**POST** `/tasks` (Protected)
```json
Request:
{
  "title": "New Task",
  "description": "Task description"
}

Response (201):
{
  "_id": "507f1f77bcf86cd799439012",
  "title": "New Task",
  "description": "Task description",
  "completed": false,
  "userId": "507f1f77bcf86cd799439011",
  "createdAt": "2025-12-12T10:30:00Z"
}
```

### Update Task
**PUT** `/tasks/:id` (Protected)
```json
Request:
{
  "title": "Updated Title",
  "description": "Updated description",
  "completed": true
}

Response (200):
{
  "_id": "507f1f77bcf86cd799439012",
  "title": "Updated Title",
  "description": "Updated description",
  "completed": true
}
```

### Delete Task
**DELETE** `/tasks/:id` (Protected)
```json
Response (200):
{
  "message": "Task deleted successfully"
}
```

## Error Responses

### 400 Bad Request
```json
{ "error": "Email, password, and name are required" }
```

### 401 Unauthorized
```json
{ "error": "Invalid credentials" }
```

### 500 Server Error
```json
{ "error": "Internal Server Error" }
```
