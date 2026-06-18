# Final Project Readme
# Product Feedback Analyzer

A backend-based feedback management and analytics platform built using **Node.js, Express.js, and MongoDB**. The system enables users to submit feedback, vote on feature requests, and provides product managers with analytics-driven insights for prioritizing product development.

---

## Project Overview

Product Feedback Analyzer is designed to centralize customer feedback collection and analysis. Users can submit feature requests, bug reports, and improvement suggestions, while other users can vote on existing feedback instead of creating duplicate requests.

The system uses MongoDB aggregation pipelines to generate meaningful analytics such as top requested features, category-wise statistics, status distribution, and monthly feedback trends.

---

## Features

### User Management

* Create users
* Retrieve all users
* User role support (User / Manager)

### Feedback Management

* Create feedback
* View all feedback
* View feedback by ID
* Update feedback
* Delete feedback
* Search feedback by keyword
* Filter feedback by category and status

### Voting System

* Vote on feedback requests
* Prevent duplicate votes
* Track feature popularity

### Analytics Dashboard

* Total Users
* Total Feedback
* Total Votes
* Open Requests
* Completed Requests

### Advanced Analytics

* Most Requested Features
* Category Statistics
* Status Statistics
* Monthly Feedback Trends

### API Documentation

* Swagger UI Integration
* Interactive API Documentation

---

## System Workflow

```text
User Creates Account
        ↓
User Submits Feedback
        ↓
Feedback Stored in MongoDB
        ↓
Users Vote on Feedback
        ↓
Product Managers Review Requests
        ↓
Analytics Generated
        ↓
Features Prioritized Based on Demand
```

---

## Tech Stack

### Backend

* Node.js
* Express.js

### Database

* MongoDB
* Mongoose

### API Testing

* Postman

### API Documentation

* Swagger UI
* Swagger JSDoc

### Development Tools

* Visual Studio Code
* Nodemon
* Git
* GitHub

---

## Project Structure

```text
productfeedback/
│
├── config/
│   └── db.js
│
├── controllers/
│   ├── analyticsController.js
│   ├── feedbackController.js
│   ├── userController.js
│   └── voteController.js
│
├── docs/
│   └── swagger.js
│
├── models/
│   ├── Feedback.js
│   ├── User.js
│   └── Vote.js
│
├── routes/
│   ├── analyticsRoutes.js
│   ├── feedbackRoutes.js
│   ├── userRoutes.js
│   └── voteRoutes.js
│
├── .env
├── package.json
├── seed.js
├── server.js
└── README.md
```

---

## Database Design

### User Collection

```json
{
  "name": "John Doe",
  "email": "john@gmail.com",
  "role": "user"
}
```

### Feedback Collection

```json
{
  "title": "Dark Mode",
  "description": "Add dark theme support",
  "category": "Feature Request",
  "status": "Open",
  "createdBy": "USER_ID"
}
```

### Vote Collection

```json
{
  "user": "USER_ID",
  "feedback": "FEEDBACK_ID"
}
```

---

## MongoDB Relationships

### One-to-Many

```text
User → Feedback
```

One user can create multiple feedback entries.

### One-to-Many

```text
Feedback → Votes
```

One feedback item can receive multiple votes.

### Many-to-One

```text
Vote → User
Vote → Feedback
```

---

## API Endpoints

### Users

| Method | Endpoint   |
| ------ | ---------- |
| POST   | /api/users |
| GET    | /api/users |

---

### Feedback

| Method | Endpoint                           |
| ------ | ---------------------------------- |
| POST   | /api/feedback                      |
| GET    | /api/feedback                      |
| GET    | /api/feedback/:id                  |
| PUT    | /api/feedback/:id                  |
| DELETE | /api/feedback/:id                  |
| GET    | /api/feedback/search?keyword=value |

---

### Votes

| Method | Endpoint   |
| ------ | ---------- |
| POST   | /api/votes |
| GET    | /api/votes |

---

### Analytics

| Method | Endpoint                      |
| ------ | ----------------------------- |
| GET    | /api/analytics/dashboard      |
| GET    | /api/analytics/top-features   |
| GET    | /api/analytics/categories     |
| GET    | /api/analytics/status         |
| GET    | /api/analytics/monthly-trends |

---

## Installation

### Clone Repository

```bash
git clone https://github.com/rudrakxh11/FacePrep-MongoDB-couse.git
cd productfeedback
```

### Install Dependencies

```bash
npm install
```

### Configure Environment Variables

Create a `.env` file:

```env
PORT=4000
MONGO_URI=mongodb://127.0.0.1:27017/productFeedbackDB
```

### Run Application

```bash
npm run dev
```

Server:

```text
http://localhost:4000
```

---

## Database Seeding

Populate the database with sample data:

```bash
node seed.js
```

This generates:

```text
20 Users
50 Feedback Records
100 Votes
Multiple Feedback Statuses
```

---

## Swagger Documentation

Open Swagger UI:

```text
http://localhost:4000/api-docs
```

Swagger provides interactive API documentation and endpoint testing.

---

## Sample Analytics Output

### Dashboard

```json
{
  "totalUsers": 20,
  "totalFeedback": 50,
  "totalVotes": 100,
  "openRequests": 11,
  "completedRequests": 8
}
```

### Top Features

```json
[
  {
    "title": "Dark Mode",
    "category": "Feature Request",
    "totalVotes": 5
  }
]
```

---

## Learning Outcomes

* REST API Development
* MongoDB CRUD Operations
* MongoDB Relationships
* Aggregation Pipelines
* Search and Filtering
* API Documentation using Swagger
* Backend Architecture using Express.js
* Database Seeding and Testing
* Git and GitHub Project Management

---

## Author

**Rudraksh Mishra**

B.Tech CSE Student

Product Feedback Analyzer | MongoDB + Node.js + Express.js
