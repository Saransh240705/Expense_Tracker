## Installation

1. Clone the repository:
   ```
   git clone <repository-url>
   cd expense-tracker
   ```

2. Create and activate a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirement.txt
   ```

4. Set environment variables:
   ```
   export FLASK_APP=app.py
   export FLASK_ENV=development
   ```
   On Windows:
   ```
   set FLASK_APP=app.py
   set FLASK_ENV=development
   ```

5. Initialize the database:
   ```
   flask db init
   flask db migrate -m "Initial migration"
   flask db upgrade
   ```

6. Run the application:
   ```
   flask run
   ```
   or
   ```
   python run.py
   ```

   ## Project Structure

- `app.py`: Main Flask application file
- `config.py`: Configuration settings
- `models.py`: Database models
- `forms.py`: Form classes using Flask-WTF
- `expense_tracker.db`: SQLite database file
- `db_init.py`: Database initialization script
- `static/`: Static files (CSS, JS)
- `templates/`: HTML templates


# Expense Tracker Application

A comprehensive Flask-based expense tracking system designed to help users manage their personal finances efficiently.

## Project Overview

This expense tracker allows users to monitor their spending habits by categorizing expenses, generating visual reports, and maintaining a detailed transaction history. The application demonstrates the implementation of a full-stack web application using Python Flask framework and SQLite database.

## Technical Stack & Justification

### Backend
- **Flask (2.0.1)**: Chosen for its lightweight nature and flexibility in building web applications
  - Easy to scale
  - Extensive documentation
  - Large community support
  - Minimal boilerplate code

- **SQLAlchemy (1.4.23)**: Used as ORM (Object-Relational Mapper)
  - Abstracts database operations
  - Provides database agnostic code
  - Simplifies data modeling
  - Prevents SQL injection attacks

- **Flask-Login (0.5.0)**: Handles user authentication
  - Session management
  - User authorization
  - Secure password handling
  - Remember me functionality

### Frontend
- **Bootstrap 5**: Responsive design framework
  - Mobile-first approach
  - Consistent UI components
  - Grid system for layouts
  - Cross-browser compatibility

- **Chart.js**: Data visualization library
  - Interactive charts
  - Responsive graphs
  - Multiple chart types
  - Customizable appearances

### Database
- **SQLite**: Lightweight, serverless database
  - Zero-configuration
  - File-based storage
  - ACID compliant
  - Perfect for development and small to medium applications

## Key Features & Implementation Details

1. **User Authentication System**
   - Secure password hashing using Werkzeug
   - Session management with Flask-Login
   - Email verification
   - Password reset functionality

2. **Expense Management**
   - CRUD operations for expenses
   - Category-based organization
   - Date-wise tracking
   - Amount validation

3. **Category System**
   - Dynamic category creation
   - Category-wise expense tracking
   - Default categories for new users
   - Category deletion protection

4. **Reporting System**
   - Monthly summaries
   - Category-wise distribution
   - Visual representations using Chart.js
   - Exportable reports

## Database Schema

### Users Table
```sql
CREATE TABLE user (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username VARCHAR(64) UNIQUE NOT NULL,
    email VARCHAR(120) UNIQUE NOT NULL,
    password_hash VARCHAR(128)
);
```

### Categories Table
```sql
CREATE TABLE category (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name VARCHAR(64) NOT NULL,
    user_id INTEGER NOT NULL,
    FOREIGN KEY (user_id) REFERENCES user (id)
);
```

### Expenses Table
```sql
CREATE TABLE expense (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    description VARCHAR(140),
    amount FLOAT NOT NULL,
    date DATETIME NOT NULL,
    user_id INTEGER NOT NULL,
    category_id INTEGER NOT NULL,
    FOREIGN KEY (user_id) REFERENCES user (id),
    FOREIGN KEY (category_id) REFERENCES category (id)
);
```

## Security Features

1. **Password Security**
   - Bcrypt hashing
   - Salt generation
   - Minimum password requirements

2. **Form Protection**
   - CSRF protection
   - Input validation
   - XSS prevention

3. **Session Security**
   - Secure cookie handling
   - Session timeout
   - Remember-me token encryption

## Development Setup

1. **Environment Setup**
   ```bash
   python -m venv venv
   venv\Scripts\activate
   pip install -r requirements.txt
   ```

2. **Environment Variables**
   ```bash
   set FLASK_APP=app.py
   set FLASK_ENV=development
   set SECRET_KEY=your-secret-key
   ```

3. **Database Initialization**
   ```bash
   flask db init
   flask db migrate -m "Initial migration"
   flask db upgrade
   ```

## Testing

1. **Unit Tests**
   - Route testing
   - Model testing
   - Form validation testing

2. **Integration Tests**
   - User workflow testing
   - Database operations
   - Authentication flow

## Common Interview Questions

1. **Why Flask over Django?**
   - Lightweight framework
   - More flexibility
   - Better for small to medium applications
   - Easier learning curve

2. **Database Choice Justification**
   - SQLite for development
   - Easy migration to PostgreSQL for production
   - No separate server required
   - Built-in Python support

3. **Security Implementations**
   - Password hashing
   - CSRF protection
   - SQL injection prevention
   - XSS protection

4. **Scalability Considerations**
   - Modular design
   - Database indexing
   - Caching implementation
   - API architecture

## Future Enhancements

1. **Technical Improvements**
   - Add API endpoints
   - Implement caching
   - Add export functionality
   - Email notifications

2. **Feature Additions**
   - Budget planning
   - Recurring expenses
   - Multi-currency support
   - File attachments for receipts

## Contributors
- Aaysha Sinha - 2024UIC3637
- Saransh - 2024UIC3640
- Prithvi Vijay Sharma - 2024UIC3613
- Jay Singh - 2024UIC3653
