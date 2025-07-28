# Learning Management System (LMS)

A comprehensive Learning Management System built with React for the frontend and Spring Boot for the backend, designed to facilitate online learning, course management, and educational content delivery.

## 🌟 Features

### Core Functionality
- **User Management**: Role-based access control for students, instructors, and administrators
- **Course Management**: Create, edit, and organize courses with multimedia content
- **Authentication**: Secure login system with JWT tokens and Google OAuth integration
- **Progress Tracking**: Monitor student progress and course completion
- **Assessment System**: Create and manage quizzes, assignments, and evaluations
- **Email Notifications**: Automated email system for course updates and communications
- **AI Integration**: OpenAI integration for enhanced learning experiences

### User Roles
- **Students**: Enroll in courses, track progress, complete assessments
- **Instructors**: Create and manage courses, monitor student performance
- **Administrators**: Manage users, courses, and system-wide settings

## 🛠️ Tech Stack

### Frontend
- **React**: Modern JavaScript library for building user interfaces
- **JavaScript/TypeScript**: For application logic and type safety

### Backend
- **Spring Boot**: Java-based framework for building robust backend services
- **Spring Security**: Authentication and authorization
- **MySQL**: Relational database for data persistence
- **JWT**: JSON Web Tokens for secure authentication

### Third-Party Integrations
- **Google OAuth**: Social authentication
- **OpenAI API**: AI-powered features
- **Email Service**: Gmail integration for notifications
- **Webhooks**: Real-time event handling

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **Java 11** or higher
- **Maven** (for Spring Boot)
- **MySQL** (v8.0 or higher)
- **Git**

## ⚙️ Environment Variables

Create a `.env` file in the root directory and configure the following variables:

```bash
# Frontend Configuration
FRONTEND_URL=http://localhost:3000

# Backend Configuration
BACKEND_URL=http://localhost:8080

# Database Configuration
MYSQL_URL=jdbc:mysql://localhost:3306/lms_db
MYSQLUSER=your_mysql_username
MYSQLPASSWORD=your_mysql_password

# JWT Configuration
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRATION=86400000
REFRESH_TOKEN_EXPIRATION=604800000

# Google OAuth Configuration
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

# Email Configuration
GMAIL_USERNAME=your_gmail_username
GMAIL_PASSWORD=your_gmail_app_password

# Webhooks
WEBHOOK_URL=your_webhook_url

# OpenAI Integration
OPENAI_KEY=your_openai_api_key
```

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/vivekchavan14/LMS.git
cd LMS
```

### 2. Database Setup
```sql
-- Create MySQL database
CREATE DATABASE lms_db;

-- Create user (optional)
CREATE USER 'lms_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON lms_db.* TO 'lms_user'@'localhost';
FLUSH PRIVILEGES;
```

### 3. Backend Setup (Spring Boot)
```bash
# Navigate to backend directory
cd backend

# Install dependencies and run
mvn clean install
mvn spring-boot:run
```

The backend server will start on `http://localhost:8080`

### 4. Frontend Setup (React)
```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start development server
npm start
```

The frontend application will start on `http://localhost:3000`

## 📁 Project Structure

```
LMS/
├── backend/                    # Spring Boot backend
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/lms/
│   │   │   │       ├── controller/    # REST API controllers
│   │   │   │       ├── service/       # Business logic
│   │   │   │       ├── model/         # Entity models
│   │   │   │       ├── repository/    # Data access layer
│   │   │   │       └── config/        # Configuration classes
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   └── pom.xml
├── frontend/                   # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/         # Reusable components
│   │   ├── pages/              # Page components
│   │   ├── services/           # API services
│   │   ├── utils/              # Utility functions
│   │   ├── hooks/              # Custom React hooks
│   │   └── styles/             # CSS/styling files
│   ├── package.json
│   └── README.md
└── docs/                       # Documentation
```

## 🔧 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/google` - Google OAuth login
- `POST /api/auth/refresh` - Refresh JWT token
- `POST /api/auth/logout` - User logout

### Courses
- `GET /api/courses` - Get all courses
- `GET /api/courses/{id}` - Get course by ID
- `POST /api/courses` - Create new course
- `PUT /api/courses/{id}` - Update course
- `DELETE /api/courses/{id}` - Delete course

### Users
- `GET /api/users` - Get all users (admin only)
- `GET /api/users/{id}` - Get user by ID
- `PUT /api/users/{id}` - Update user profile
- `DELETE /api/users/{id}` - Delete user (admin only)

### Enrollments
- `POST /api/enrollments` - Enroll in course
- `GET /api/enrollments/user/{userId}` - Get user enrollments
- `DELETE /api/enrollments/{id}` - Unenroll from course

## 🧪 Testing

### Backend Testing
```bash
cd backend
mvn test
```

### Frontend Testing
```bash
cd frontend
npm test
```

## 🚀 Deployment

### Backend Deployment
1. Build the application:
   ```bash
   mvn clean package
   ```

2. Run the JAR file:
   ```bash
   java -jar target/lms-backend-1.0.0.jar
   ```

### Frontend Deployment
1. Build for production:
   ```bash
   npm run build
   ```

2. Deploy the `build` folder to your web server

### Docker Deployment (Optional)
```bash
# Build and run with Docker Compose
docker-compose up --build
```

## 📚 Usage

1. **Admin Setup**: Create an admin account and configure system settings
2. **Course Creation**: Instructors can create courses with multimedia content
3. **Student Enrollment**: Students can browse and enroll in available courses
4. **Progress Tracking**: Monitor learning progress and completion rates
5. **Assessments**: Take quizzes and complete assignments
6. **Certificates**: Generate completion certificates



