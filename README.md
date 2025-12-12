# Frontend Developer Internship Project

A modern, scalable full-stack web application built with React, Node.js/Express, JWT authentication, and MongoDB.

## Tech Stack
- **Frontend:** React.js, TailwindCSS, Axios, React Router
- **Backend:** Node.js, Express.js, MongoDB, JWT
- **Security:** bcryptjs, CORS, Environment Variables

## Key Features

### Authentication System
- User registration and login
- JWT-based authentication
- Password hashing with bcryptjs
- Protected routes and endpoints
- Secure logout

### Dashboard Features
- Authenticated user profile display
- Task CRUD operations
- Search and filter functionality
- Responsive UI design

### Security Implementation
- Client-side form validation
- Server-side input validation  
- JWT middleware for protected routes
- Secure password storage
- CORS configuration

## Installation

### Backend Setup
```bash
cd server
npm install
# Configure .env with MongoDB URI and JWT_SECRET
npm start
```

### Frontend Setup  
```bash
cd client
npm install
# Configure .env with API_URL
npm start
```

## API Endpoints

**Auth Routes:**
- POST /api/auth/signup
- POST /api/auth/login
- POST /api/auth/logout

**Task Routes:**
- GET /api/tasks
- POST /api/tasks
- PUT /api/tasks/:id
- DELETE /api/tasks/:id

## Project Structure
- client/ - React frontend
- server/ - Node.js backend
- docs/ - API documentation

## Scalability Notes

**Frontend:**
- Modular component architecture
- Service layer abstraction
- Ready for state management integration
- Lazy loading support

**Backend:**
- RESTful API design
- Middleware-based structure
- Database indexing
- Horizontal scaling ready

**Database:**
- Connection pooling
- Query optimization
- Backup mechanisms

## Code Quality
- Clean, readable code
- Error handling throughout
- Input validation
- Comprehensive comments
- DRY principles

## Status
Project completed and ready for evaluation.
