# Welcome to your Expo app 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
   npx expo start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

# 📚 School SaaS Platform (LMS + AI Analytics)

A multi-tenant, AI-powered School Management System supporting elementary (grades 1–8) and high school (grades 9–12) institutions.

---

## 🚀 Overview

This platform is a full-scale **School Management SaaS (LMS + AI Analytics)** designed for scalability, intelligence, and multi-school isolation.

It integrates:

- 🌐 Web App (Next.js)
- 📱 Mobile App (Expo React Native)
- ⚙️ Backend API (Node.js + Express + Prisma)
- 🤖 ML Service (FastAPI + Random Forest)
- 🗄️ PostgreSQL + Redis + BullMQ

---

## 🏗️ Architecture Overview

                 ┌──────────────┐
                 │  Web (Next)  │
                 └──────┬───────┘
                        │
                 ┌──────▼───────┐
                 │ Mobile (Expo)│
                 └──────┬───────┘
                        │
                ┌───────▼────────┐
                │  API Gateway    │
                │ Node.js + API   │
                └───────┬────────┘
                        │
        ┌───────────────┼────────────────┐
        │               │                │
 ┌──────▼──────┐ ┌──────▼──────┐ ┌──────▼──────┐
 │ PostgreSQL   │ │ Redis Cache │ │ BullMQ Jobs │
 └──────┬──────┘ └──────┬──────┘ └──────┬──────┘
        │               │                │
        └───────────────┼────────────────┘
                        │
                ┌───────▼────────┐
                │ ML Service      │
                │ FastAPI + RF    │
                └─────────────────┘

---

## 🧠 Core Features

### 🏫 Multi-School SaaS
- Fully isolated multi-tenant architecture
- School admin onboarding system
- Role-Based Access Control (RBAC)

---

### 👥 User System
Roles:
- Super Admin
- School Admin
- Teacher
- Student
- Parent

---

### 🎓 Academic System
- Student management
- Teacher management
- Classes & subjects
- Student enrollment system
- Attendance tracking
- Assignments & submissions
- Gradebook system

---

### 📊 Analytics & AI
- Student performance tracking
- Attendance trend analysis
- Dropout/failure risk prediction
- ML-powered insights via FastAPI

---

### 💬 Communication
- Thread-based messaging system
- School announcements
- Email notifications (event-driven)

---

### ⚡ Production Systems
- Redis caching
- Background job processing (BullMQ)
- File uploads (assignments & submissions)
- Rate limiting
- Centralized logging

---

## 🏗️ Backend Architecture

### Pattern

Controller → Service → Repository


### Module Structure

src/modules/
├── auth/
├── schools/
├── users/
├── students/
├── teachers/
├── classes/
├── enrollment/
├── attendance/
├── assignments/
├── submissions/
├── gradebook/
├── messaging/
├── analytics/
├── dashboard/
├── ml/
├── predictions/


---

## 🤖 ML System

### 🎯 Purpose
- Predict student risk levels
- Identify at-risk students
- Support academic interventions

### 📊 Features Used
- Attendance rate
- Average grade
- Submission rate
- Late submission count

### 🔁 Flow

Postgres → Analytics Layer → ML Gateway → FastAPI → Prediction → Storage


### 🧠 AI Output Example
```json
{
  "studentId": "abc123",
  "riskLevel": 2,
  "confidence": 0.87,
  "attendanceRate": 0.62,
  "avgGrade": 58.4
}

---
### ⚙️ Tech Stack
- Backend
- Node.js
- Express.js
- Prisma ORM
- PostgreSQL
- Redis
- BullMQ
- Frontend (Web)
- Next.js (App Router)
- TypeScript
- Tailwind CSS
- Zustand
- React Query
- Mobile
- Expo React Native
- TypeScript
- ML Service
- FastAPI
- Python
- Scikit-learn (Random Forest)
- Joblib
### 🔐 Security
JWT Authentication
Role-Based Access Control (RBAC)
Multi-tenant isolation (schoolId scoping)
Rate limiting middleware
Input validation per module
###⚡ Performance Strategy
Redis caching for analytics & predictions
Background ML inference jobs
Lazy dashboard aggregation
Indexed PostgreSQL queries
Separation of read vs compute operations
###📦 Background Jobs (BullMQ)
Jobs
ML prediction processing
Email notifications
Analytics batch computation
### 📁 File Uploads
Supported
Assignment attachments
Student submissions
Storage Paths
/uploads/assignments
/uploads/submissions
### 📊 API Base URL
/api/v1
### 🧪 Example Endpoints
Auth
POST /api/v1/auth/login
Students
GET /api/v1/students
POST /api/v1/students
Attendance
POST /api/v1/attendance/mark
Assignments
POST /api/v1/assignments
Predictions
GET /api/v1/predictions/student/:id
Dashboard
GET /api/v1/dashboard/overview
### 🚀 Deployment
Environment Variables
DATABASE_URL=
JWT_SECRET=
REDIS_HOST=
ML_SERVICE_URL=
SMTP_HOST=
Services
API → Node.js server
ML Service → FastAPI container
Database → PostgreSQL
Cache → Redis
Queue → BullMQ worker
### 🧠 System Maturity
Layer	Status
Auth System	✅
School Core	✅
LMS Features	✅
Messaging	✅
Analytics	✅
AI/ML	✅
Production Layer	✅
### 📈 Future Enhancements
Real-time WebSockets (live attendance)
Mobile push notifications
AI auto-grading
Smart timetable optimization
Parent portal expansion
Offline mobile LMS mode
### 👨‍💻 Project Philosophy
Feature-first architecture
Domain-driven modules 
API as single source of truth
ML as isolated microservice
Scalable multi-tenant SaaS design
### 📌 Summary

A production-ready, AI-powered, multi-tenant School Management SaaS platform combining:

LMS functionality
Real-time analytics
Machine learning predictions
Scalable backend architecture
Multi-platform support (Web + Mobile) 