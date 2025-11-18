# LearnHub - Modern Learning Management Platform

A comprehensive full-stack Learning Management System (LMS) built with the MERN stack, featuring separate dashboards for administrators, teachers, and students with complete course management, assignments, attendance tracking, and note-taking capabilities.

![LearnHub](https://img.shields.io/badge/Version-1.0.0-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Node](https://img.shields.io/badge/Node-24.x-brightgreen)
![React](https://img.shields.io/badge/React-18.2-blue)

## Features

### Admin Dashboard
- **User Management**: Create, edit, and manage users (students, teachers, admins)
- **Course Approval**: Review and publish courses created by teachers
- **System Statistics**: Overview of total users, courses, and platform metrics
- **Admin Creation**: Secure admin-only access to create new administrators

### Teacher Dashboard
- **Course Management**: Create, edit, and publish courses with rich content
- **Assignment Creation**: Design assignments with deadlines, scoring, and file uploads
- **Attendance Tracking**: Mark and manage student attendance with Present/Absent/Late status
- **Submission Review**: Grade student assignments and provide detailed feedback
- **Student Analytics**: Track student progress and engagement
- **Advanced Filtering**: Filter courses, assignments, and attendance by multiple criteria

### Student Dashboard
- **Course Enrollment**: Browse and enroll in published courses
- **Assignment Submission**: Submit assignments with text and file uploads
- **Progress Tracking**: Monitor course completion and grades
- **Note Taking**: Create, organize, and tag notes with course linking
- **Attendance Records**: View personal attendance history across all courses
- **Smart Filters**: Filter assignments (All/Pending/Submitted), notes by course, and attendance by status

### Public Pages
- **Home Page**: Engaging landing page with platform features
- **Courses Catalog**: Browse 6+ sample courses with search and filters
- **About Page**: Information about the platform and mission
- **Contact Page**: Get in touch with support
- **Learner's Journey**: Resources and guidance for students
- **Instructor's Academy**: Information for educators

## Tech Stack

### Frontend
- **React 18.2.0** - Modern UI library
- **React Router DOM 6.15.0** - Client-side routing
- **Axios 1.5.0** - HTTP client
- **Lucide React 0.284.0** - Beautiful icon system
- **CSS3** - Custom styling with CSS variables

### Backend
- **Node.js** - JavaScript runtime
- **Express.js 4.18.2** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose 7.5.0** - MongoDB ODM
- **JWT** - Authentication and authorization
- **bcryptjs 2.4.3** - Password hashing

## Prerequisites

- Node.js (v14 or higher)
- MongoDB Atlas account or local MongoDB installation
- npm or yarn package manager

## Installation

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/learnhub.git
cd learnhub
```

### 2. Backend Setup
```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:
```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d
NODE_ENV=development
```

### 3. Frontend Setup
```bash
cd frontend
npm install
```

Create a `.env` file in the frontend directory:
```env
REACT_APP_API_URL=http://localhost:5000/api
```

### 4. Seed Sample Data (Optional)
```bash
cd backend
node seedCourses.js
```
This creates 6 sample courses with various categories and levels.

## Running the Application

### Start Backend Server
```bash
cd backend
npm run dev
```
Backend runs on `http://localhost:5000`

### Start Frontend Server
```bash
cd frontend
npm start
```
Frontend runs on `http://localhost:3000`

## Project Structure

```
learnhub/
├── backend/
│   ├── models/
│   │   ├── User.js
│   │   ├── Course.js
│   │   ├── Enrollment.js
│   │   ├── Assignment.js
│   │   ├── Attendance.js
│   │   └── Note.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── users.js
│   │   ├── courses.js
│   │   ├── enrollments.js
│   │   ├── assignments.js
│   │   ├── attendance.js
│   │   └── notes.js
│   ├── middleware/
│   │   └── auth.js
│   ├── seedCourses.js
│   ├── server.js
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.js
│   │   │   └── Footer.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── pages/
│   │   │   ├── Home.js
│   │   │   ├── Login.js
│   │   │   ├── Register.js
│   │   │   ├── Courses.js
│   │   │   ├── AdminDashboard.js
│   │   │   ├── TeacherDashboard.js
│   │   │   ├── StudentDashboard.js
│   │   │   ├── About.js
│   │   │   ├── Contact.js
│   │   │   ├── LearnersJourney.js
│   │   │   └── InstructorsAcademy.js
│   │   ├── styles/
│   │   │   └── SharedDashboard.css
│   │   ├── utils/
│   │   │   └── api.js
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
└── README.md
```

## Default Credentials

After seeding, you can create users or use:

**Admin:**
- Email: `admin@learnhub.com`
- Password: (Set during first admin seed)

**Sample Teacher:**
- Email: `teacher@learnhub.com`
- Password: `teacher123`

## Key Features Breakdown

### Authentication & Authorization
- JWT-based authentication
- Role-based access control (Admin, Teacher, Student)
- Protected routes and API endpoints
- Secure password hashing

### Course Management
- Full CRUD operations for courses
- Course categories and difficulty levels
- Rich course details (learning outcomes, requirements, pricing)
- Course approval workflow
- Course enrollment system

### Assignment System
- Create assignments with deadlines and scoring
- File upload support for assignments
- Student submission tracking
- Grading and feedback system
- Filter by status (pending/submitted)

### Attendance Tracking
- Date-wise attendance records
- Multiple status options (Present, Absent, Late)
- Course-specific tracking
- Student attendance history
- Filtering and search capabilities

### Note Taking
- Create and organize notes
- Link notes to specific courses
- Tag system for organization
- Pin important notes
- Search and filter functionality

### Advanced Filtering
- Real-time search across all dashboards
- Multi-criteria filtering (course, status, date)
- Combined search and filter operations
- Smart empty states

## Design System

LearnHub uses a unified design system with:
- Consistent color scheme with CSS variables
- Reusable component styles
- Responsive design for all screen sizes
- Modern UI with smooth transitions
- Accessible interface elements

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user

### Courses
- `GET /api/courses` - Get all published courses
- `GET /api/courses/:id` - Get single course
- `POST /api/courses` - Create course (Teacher)
- `PUT /api/courses/:id` - Update course (Teacher)
- `DELETE /api/courses/:id` - Delete course (Teacher/Admin)

### Assignments
- `GET /api/assignments/course/:courseId` - Get course assignments
- `GET /api/assignments/my-submissions` - Get student submissions
- `POST /api/assignments` - Create assignment (Teacher)
- `POST /api/assignments/:id/submit` - Submit assignment (Student)
- `PUT /api/assignments/:id/grade` - Grade assignment (Teacher)

### Attendance
- `GET /api/attendance/course/:courseId` - Get course attendance
- `GET /api/attendance/my-attendance` - Get student attendance
- `POST /api/attendance` - Create attendance record (Teacher)
- `PUT /api/attendance/:id` - Update attendance (Teacher)

### Notes
- `GET /api/notes/my-notes` - Get all student notes
- `GET /api/notes/course/:courseId` - Get course-specific notes
- `POST /api/notes` - Create note (Student)
- `PUT /api/notes/:id` - Update note (Student)
- `DELETE /api/notes/:id` - Delete note (Student)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Developer

Built by Syntax Squad

## Acknowledgments

- MongoDB Atlas for database hosting
- Unsplash for sample course images
- Lucide React for beautiful icons
- The MERN stack community


Star this repository if you find it helpful!
