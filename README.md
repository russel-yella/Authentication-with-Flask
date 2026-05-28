# Flask Authentication System

A secure user authentication system built with Flask, Flask-Login, SQLAlchemy, and SQLite.

## Features

* User Registration
* Secure Password Hashing
* User Login & Logout
* Remember Me Functionality
* Protected Routes
* SQLite Database Integration
* File Download Protection
* Flash Messages for Authentication Errors

---

## Technologies Used

* Python
* Flask
* Flask-Login
* Flask-SQLAlchemy
* SQLite
* Werkzeug Security

---

## Project Structure

```bash
project/
│
├── static/
│   └── files/
│       └── cheat_sheet.pdf
│
├── templates/
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   └── secrets.html
│
├── users.db
├── app.py
└── requirements.txt
```

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/flask-auth-system.git
cd flask-auth-system
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

#### Windows

```bash
venv\Scripts\activate
```

#### macOS/Linux

```bash
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Required Packages

Create a `requirements.txt` file with:

```txt
Flask
Flask-SQLAlchemy
Flask-Login
Werkzeug
```

Or generate automatically:

```bash
pip freeze > requirements.txt
```

---

## Running the Application

```bash
python app.py
```

The application will start at:

```bash
http://127.0.0.1:5000
```

---

## Authentication Flow

### Registration

* Users create an account with:

  * Name
  * Email
  * Password
* Passwords are securely hashed before storage.

### Login

* Users authenticate using email and password.
* Session management handled by Flask-Login.

### Protected Routes

Routes decorated with:

```python
@login_required
```

can only be accessed by authenticated users.

---

## Database

The project uses SQLite with SQLAlchemy ORM.

### User Model

```python
class User(UserMixin, db.Model):
    id = mapped_column(Integer, primary_key=True)
    email = mapped_column(String(100), unique=True)
    password = mapped_column(String(100))
    name = mapped_column(String(100))
```

---

## Security Features

* Password hashing using Werkzeug
* Session-based authentication
* Protected routes
* Remember-me cookies
* Secure login validation

---

## Future Improvements

* Email verification
* Password reset functionality
* User profile page
* OAuth login (Google/GitHub)
* CSRF protection with Flask-WTF
* Environment variable configuration

---

## Example Routes

| Route       | Description             |
| ----------- | ----------------------- |
| `/`         | Home page               |
| `/register` | User registration       |
| `/login`    | User login              |
| `/logout`   | Logout user             |
| `/secrets`  | Protected page          |
| `/download` | Protected file download |

---
