
# 🍽️ SYNERGY - BookTable



---

## 📋 Table of Contents
- [📌 Project Overview](#project-overview)
- [✨ Features](#features)
- [🚀 Tech Stack](#tech-stack)
- [🏗️ Architecture Design](#architecture-design)
- [📝 Project Journal](#project-journal)
- [🧰 Getting Started](#getting-started)
  - [📦 Prerequisites](#prerequisites)
  - [⚙️ Backend Setup](#backend-setup)
  - [💻 Frontend Setup](#frontend-setup)
- [▶️ Running the Application](#running-the-application)
- [🚀 Deployment](#deployment)
- [🔄 CI/CD](#cicd)
- [🤝 Contributing](#contributinons)
- [💡 XP Core Values](#xp-core-values)

---

## Project Overview
SYNERGY, also known as BookTable, is a comprehensive online restaurant reservation platform for customers, restaurant managers, and administrators. It features location-based search, real-time booking, user profiles, and a review system to enhance the dining experience.

---

## Features

### 🔐 User Authentication
- AWS Cognito with OTP-based login and role-based access via Cognito Groups

### 📍 Restaurant Discovery
- Location-based search (MySQL spatial + Google Maps API)
- View locations on Google Maps
- Nearby restaurant suggestions
- User can see any restaurant number of bookings on a particular day

### 📅 Booking Management
- Booking and cancellation with real-time conflict detection
- Email confirmations via AWS SES and Thymeleaf templates

### 🙋‍♂️ User Experience
- Personalized home & profile pages
- View restaurants and available time slots

### 🧑‍🍳 Restaurant Manager Portal
- Add/update restaurant details
- Upload images via AWS S3 pre-signed URLs
- View and manage dashboard

### 🛡️ Admin Portal
- Admin dashboard with analytics
- Approve/reject/remove restaurants

### ⭐ Ratings and Reviews
- Users can submit & view reviews and ratings

---

## Tech Stack
- **Frontend:** Next.js, React, Material-UI
- **Backend:** Spring Boot (Java 17), Gradle
- **Database:** MySQL
- **Authentication:** AWS Cognito, Spring Security, JWTs
- **Cloud Services:**
  - AWS Elastic Beanstalk, EC2, Docker, ECR
  - AWS S3, SES, Lambda
- **APIs:** Google Maps GeoAPI

---

## Architecture Design
- RESTful API architecture
- JWTs stored in HTTP-only cookies
- Role-based access (CUSTOMER, MANAGER, ADMIN)
- Modular backend layers: controllers, services, repositories
- Component-based frontend with Next.js
- Deployed using Docker containers on AWS Elastic Beanstalk

- [Figma Design](https://www.figma.com/design/yigtQrOAV7XX2CaLXjabAl/SynergyCMPE202?node-id=22-1221&t=t2yjRMXyx6Cgmn8f-0)
- [Confluence Docs](https://cmpe-202-synergy.atlassian.net/wiki/spaces/SCRUM/pages/1376379/BookTable+-+Product+Description)


---

## Getting Started

### Prerequisites
- Node.js (v18.x or v20.x)
- JDK 17
- Gradle (uses wrapper)
- Docker
- AWS CLI (with configured credentials)
- MySQL instance

**Environment Variables**

**Backend:** (`application.properties`):
DB_URL, DB_USERNAME, DB_PASSWORD
AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_REGION
SPRING_SECURITY_OAUTH2_JWT_ISSUER_URI
AWS_COGNITO_USER_POOL_ID, AWS_COGNITO_CLIENT_ID, AWS_COGNITO_CLIENT_SECRET
AWS_COGNITO_REGION, AWS_S3_BUCKET, GOOGLE_API_KEY, APP_BASE_URL, AWS_SES_FROM_EMAIL

**Frontend:** (`.env.local`):
NEXT_PUBLIC_BASE_URL, NEXT_PUBLIC_PLACES_API_KEY

### Backend Setup
```bash
cd backend/bookTable
chmod +x ./gradlew
./gradlew clean build
./gradlew bootRun
```
### Frontend Setup
```bash
cd open-table-frontend
npm install
npm run dev
```
### Running the Application
**Backend API**: http://localhost:8080
**Frontend UI**: http://localhost:3000

### Deployment
- Backend: Dockerized, pushed to ECR, deployed via Elastic Beanstalk
- Frontend: Deployed to FrontEnd

### CI/CD
- CI/CD with GitHub Actions
- backend-ci-cd.yml: builds, tests, pushes to ECR, deploys to Elastic Beanstalk
- codeql.yml: scans Java/Kotlin codebase

**In-Repo Docs:**

**Team Roles & Contributions**

**Design Decisions**

**XP Core Values**



### XP Core Values
- Communication: Stand-ups, Figma, Confluence, transparency
- Courage: Embraced new tech, role expansions, learned AWS stack
- Respect: Code reviews, professionalism, empathy, shared ownership

Read more in our XP Core Values Document
