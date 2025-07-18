# MERN Bug Tracker

A comprehensive bug tracking application built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring extensive testing, debugging capabilities, and modern development practices.

## 🚀 Features

### Core Functionality

- **Bug Management**: Create, read, update, and delete bug reports
- **Advanced Filtering**: Filter bugs by status, severity, priority, and search functionality
- **Pagination**: Efficient handling of large datasets
- **Statistics Dashboard**: Real-time bug statistics and analytics
- **Responsive Design**: Mobile-friendly interface with Tailwind CSS

### Bug Report Features

- Detailed bug information (title, description, severity, priority, status)
- Steps to reproduce, expected vs actual behavior
- Tag system for categorization
- Assignment tracking
- Creation and update timestamps
- Age calculation for bugs

### Technical Features

- **RESTful API** with Express.js
- **MongoDB** with Mongoose ODM
- **React** with Context API for state management
- **Form Validation** with react-hook-form and express-validator
- **Error Handling** with custom middleware and error boundaries
- **Comprehensive Testing** with Jest and React Testing Library
- **Debugging Tools** and logging utilities

## 🛠️ Tech Stack

### Backend

- **Node.js** with Express.js
- **MongoDB** with Mongoose
- **Express Validator** for input validation
- **Helmet** for security headers
- **Morgan** for HTTP request logging
- **CORS** for cross-origin requests
- **Jest** and **Supertest** for testing
- **MongoDB Memory Server** for test database

### Frontend

- **React** with hooks and Context API
- **React Router** for navigation
- **React Hook Form** for form management
- **Axios** for API requests
- **Tailwind CSS** for styling
- **Lucide React** for icons
- **React Hot Toast** for notifications
- **React Testing Library** for component testing

## 📦 Installation

### Prerequisites

- Node.js (v16+ recommended)
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn

### Setup Instructions

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd mern-bug-tracker
   ```

2. **Install root dependencies**

   ```bash
   npm install
   ```

3. **Install backend dependencies**

   ```bash
   cd backend
   npm install
   ```

4. **Install frontend dependencies**

   ```bash
   cd ../frontend
   npm install
   ```

5. **Configure environment variables**

   ```bash
   cd ../backend
   cp .env.example .env
   # Edit .env with your MongoDB connection string and other settings
   ```

6. **Start MongoDB**

   - Local: `mongod`
   - Or use MongoDB Atlas cloud database

7. **Run the application**

   ```bash
   # From the root directory
   npm run dev
   ```

   Or start services separately:

   ```bash
   # Terminal 1 - Backend
   cd backend && npm run dev

   # Terminal 2 - Frontend
   cd frontend && npm run dev
   ```

8. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

## 🧪 Testing

### Running Tests

```bash
# Run all tests
npm test

# Run backend tests only
npm run test:backend

# Run frontend tests only
npm run test:frontend

# Run tests with coverage
cd frontend && npm run test:coverage
```

### Testing Strategy

#### Backend Testing

- **Unit Tests**: Individual functions and utilities
- **Integration Tests**: API endpoints with real database operations
- **Database Mocking**: MongoDB Memory Server for isolated testing
- **Error Handling**: Testing various error scenarios

#### Frontend Testing

- **Component Tests**: Individual React components
- **Integration Tests**: Component interactions and API calls
- **Form Validation**: Testing form inputs and validation
- **User Interactions**: Testing user events and state changes

### Test Coverage

- Backend: Controllers, models, utilities, middleware
- Frontend: Components, services, context, forms
- Error scenarios and edge cases
- API integration and data flow

## 🐛 Debugging

### Debugging Tools and Techniques

#### Backend Debugging

1. **Console Logging**: Custom debug utility with environment-based logging
2. **Node.js Inspector**:
   ```bash
   cd backend && npm run debug
   # Then open chrome://inspect in Chrome
   ```
3. **Morgan Logging**: HTTP request logging
4. **Error Middleware**: Comprehensive error handling and logging

#### Frontend Debugging

1. **React Developer Tools**: Component inspection and state debugging
2. **Chrome DevTools**: Network requests, console logging, performance
3. **Error Boundaries**: Graceful error handling and reporting
4. **Context Debugging**: State management debugging

#### Debug Features

- **Debug Logging**: Environment-based logging system
- **Performance Monitoring**: Request timing and memory usage
- **Error Tracking**: Comprehensive error logging and reporting
- **Network Debugging**: API request/response logging

### Common Debugging Scenarios

1. **API Issues**: Check network tab, server logs, and error responses
2. **Database Problems**: MongoDB connection, query debugging
3. **Form Validation**: Client-side and server-side validation errors
4. **State Management**: React Context debugging and state flow
5. **Performance Issues**: Component re-renders, API optimization

## 🔧 Error Handling

### Backend Error Handling

- **Custom Error Middleware**: Centralized error processing
- **Validation Errors**: Input validation with detailed messages
- **Database Errors**: MongoDB error handling and transformation
- **HTTP Status Codes**: Proper status code usage
- **Error Logging**: Comprehensive error logging system

### Frontend Error Handling

- **Error Boundaries**: React error boundary implementation
- **API Error Handling**: Axios interceptors for error processing
- **Form Validation**: Real-time validation with user feedback
- **Toast Notifications**: User-friendly error messages
- **Fallback UI**: Graceful degradation for errors

## 📁 Project Structure

```
mern-bug-tracker/
├── backend/
│   ├── controllers/         # Route controllers
│   ├── models/             # Mongoose models
│   ├── routes/             # Express routes
│   ├── middleware/         # Custom middleware
│   ├── utils/              # Utility functions
│   ├── __tests__/          # Backend tests
│   └── server.js           # Server entry point
├── frontend/
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── context/        # React Context
│   │   ├── services/       # API services
│   │   ├── __tests__/      # Frontend tests
│   │   └── App.jsx         # App component
│   ├── public/             # Static assets
│   └── index.html          # HTML template
├── package.json            # Root package.json
└── README.md              # This file
```

## 🚀 Deployment

### Backend Deployment

1. **Environment Variables**: Set production environment variables
2. **Database**: Use MongoDB Atlas for production
3. **Security**: Enable helmet, CORS configuration
4. **Logging**: Configure production logging

### Frontend Deployment

1. **Build**: `npm run build` in frontend directory
2. **Static Hosting**: Deploy to Netlify, Vercel, or similar
3. **API Configuration**: Update API base URL for production

### Full-Stack Deployment

- **Backend**: Deploy to Heroku, Railway, or DigitalOcean
- **Frontend**: Deploy to Netlify, Vercel, or GitHub Pages
- **Database**: MongoDB Atlas for production database
- **Environment**: Configure production environment variables

## 📊 API Documentation

### Endpoints

#### Bugs

- `GET /api/bugs` - Get all bugs (with filtering and pagination)
- `GET /api/bugs/:id` - Get single bug
- `POST /api/bugs` - Create new bug
- `PUT /api/bugs/:id` - Update bug
- `DELETE /api/bugs/:id` - Delete bug
- `GET /api/bugs/stats` - Get bug statistics

#### Health Check

- `GET /api/health` - Server health check

### Request/Response Examples

#### Create Bug

```json
POST /api/bugs
{
  "title": "Login button not working",
  "description": "The login button doesn't respond when clicked",
  "severity": "high",
  "priority": "high",
  "reportedBy": "John Doe",
  "stepsToReproduce": "1. Go to login page\n2. Click login button\n3. Nothing happens",
  "expectedBehavior": "Should redirect to dashboard",
  "actualBehavior": "Button doesn't respond",
  "tags": ["frontend", "authentication"]
}
```
