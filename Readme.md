# Flask Expense Tracker

A comprehensive expense tracking application built with Flask and SQLAlchemy.

## Features

- User Authentication (Register, Login, Logout)
- Add, Edit, and Delete Expenses
- Expense Categories Management
- Dashboard with Monthly Overview
- Visual Reports with Charts
- Responsive Design

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

7. Access the application at `http://localhost:5000`

## Project Structure

- `app.py`: Main Flask application file
- `config.py`: Configuration settings
- `models.py`: Database models
- `forms.py`: Form classes using Flask-WTF
- `schema.sql`: SQL schema for database setup
- `static/`: Static files (CSS, JS)
- `templates/`: HTML templates

## Technologies Used

- Flask
- SQLAlchemy
- Flask-Login for authentication
- Flask-WTF for forms
- SQLite database (can be configured for other databases)
- Bootstrap for responsive design
- Chart.js for data visualization

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
