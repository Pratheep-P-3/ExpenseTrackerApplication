# Expense Tracker

A full-stack web application for tracking personal and organizational expenses built with Spring Boot and Angular.

## 📝 Project Overview

Expense Tracker is a web-based application that helps users manage their finances by tracking expenses, categorizing them, and visualizing spending patterns through interactive charts.

**Key Features:**
- User registration and login with secure authentication
- Add, edit, and delete expenses
- Categorize expenses (Personal/Organizational)
- Filter expenses by date, type, and category
- View spending analytics with pie charts
- Create custom expense categories

## 🛠️ Technologies Used

### Backend
- **Framework:** Spring Boot 3.2.0
- **Language:** Java 21
- **Database:** MySQL 8.0
- **Security:** Spring Security with JWT
- **ORM:** Spring Data JPA

### Frontend
- **Framework:** Angular 21
- **Language:** TypeScript
- **Charts:** Chart.js
- **Styling:** CSS



### 1. Database Setup
```sql
CREATE DATABASE expense_tracker_db;
```

### 2. Backend Setup
```bash
cd backend
# Update database credentials in src/main/resources/application.yml
mvn clean install
mvn spring-boot:run
```
Backend will run on `http://localhost:8080`

### 3. Frontend Setup
```bash
cd frontend
npm install
npm start
```
Frontend will run on `http://localhost:4200`

## 🗄️ Database Schema

**Tables:**
- `users` - User account information
- `categories` - Expense categories (25 pre-seeded)
- `expenses` - Individual expense records

**Relationships:**
- One user can have many expenses
- One category can be used in many expenses

## 🔐 Authentication

- Passwords are encrypted using BCrypt
- JWT tokens for secure API access
- Token expires after 24 hours
- All endpoints except login/signup require authentication

## 📚 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | /auth/signup | Register new user | No |
| POST | /auth/login | Login user | No |
| GET | /expenses | Get all expenses | Yes |
| POST | /expenses | Create expense | Yes |
| PUT | /expenses/{id} | Update expense | Yes |
| DELETE | /expenses/{id} | Delete expense | Yes |
| GET | /categories | Get categories | Yes |
| POST | /categories | Create category | Yes |

## 🏗️ Project Structure

```
expense-tracker/
├── backend/
│   ├── src/main/java/com/expensetracker/
│   │   ├── controller/       # REST Controllers
│   │   ├── service/          # Business Logic
│   │   ├── repository/       # Database Access
│   │   ├── entity/           # JPA Entities
│   │   ├── security/         # JWT & Authentication
│   │   └── config/           # Configuration
│   └── pom.xml
└── frontend/
    ├── src/app/
    │   ├── components/       # UI Components
    │   ├── services/         # HTTP Services
    │   └── models/           # Data Models
    └── package.json
```

## 📊 Features Demonstration

### User Authentication
- Secure signup with password encryption
- Login with JWT token generation
- Auto-logout on token expiration

### Expense Management
- Create expenses with amount, date, description, type, and category
- Edit existing expenses
- Delete expenses with confirmation
- Real-time table updates

### Filtering & Search
- Filter by expense type (Personal/Organizational)
- Filter by category
- Filter by date range
- Smart date validation (end date can't be before start date)

### Analytics
- Interactive pie chart showing expenses by category
- Summary cards displaying total, personal, and organizational expenses
- Color-coded categories for easy identification

## 🔮 Future Enhancements

- [ ] Email notifications for expense reminders
- [ ] Budget setting and alerts
- [ ] Receipt image upload
- [ ] Export to Excel/PDF
- [ ] Mobile app version
- [ ] Multiple currency support
- [ ] Recurring expense templates
**Project Submitted:** [Date]  
**GitHub Repository:** [Your Repo Link]  
**Demo Video:** [YouTube/Drive Link if available]
