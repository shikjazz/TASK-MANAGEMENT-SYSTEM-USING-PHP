# TASK-MANAGEMENT-SYSTEM-USING-PHP
Overview
The Task Management System is a web application built using PHP and MySQL that allows users to register, log in, and manage their tasks efficiently. Users can add, update, delete, and track tasks in an organized manner. The project follows a simple and modular structure, making it easy to extend and customize.

Features
User Authentication:

Register new users with secure password hashing.
Login functionality with session handling.
Logout functionality.
Task Management:

Create, edit, and delete tasks.
Mark tasks as completed.
Categorize tasks based on priority.
Dashboard:

View pending and completed tasks.
Filter tasks by category.
Security Features:

Password hashing using bcrypt.
Session-based authentication.
Tech Stack
Backend: PHP (PDO for database operations)
Frontend: HTML, CSS, Bootstrap
Database: MySQL
Version Control: Git & GitHub
Installation
Prerequisites
PHP (>= 7.4)
MySQL (>= 5.7)
Apache/Nginx server
Composer (optional, if you extend the project)
Git
Steps to Install
Clone the repository

bash
Copy
Edit
git clone https://github.com/shikjazz/task-management-system.git
cd task-management-system
Setup Database

Import the database.sql file into MySQL.
Update the database credentials in config.php.
Run the application

Start your local server (e.g., XAMPP or WAMP).
Open http://localhost/task-management-system/ in your browser.
Database Structure
Run the following SQL queries to set up the database manually:

sql
Copy
Edit
CREATE DATABASE task_management;

USE task_management;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

CREATE TABLE tasks (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    task VARCHAR(255) NOT NULL,
    category VARCHAR(50),
    status ENUM('Pending', 'Completed') DEFAULT 'Pending',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
Usage
Register an Account: Navigate to /register.html and create an account.
Login: Access /login.html and enter your credentials.
Task Management: Add, update, and manage tasks from the dashboard.
Logout: Click the logout button to end the session.
Project Structure
lua
Copy
Edit
TaskManagement/
│-- index.php
│-- register.php
│-- login.php
│-- dashboard.php
│-- add_task.php
│-- edit_task.php
│-- delete_task.php
│-- mark_complete.php
│-- includes/
│   ├── config.php
│   ├── db.php
│   ├── auth.php
│-- assets/
│   ├── style.css
│-- README.md
│-- database.sql
Future Enhancements
Implement user roles and permissions.
Add email notifications for task reminders.
Improve UI with a modern front-end framework.
Deploy the project on a cloud platform.
Contributing
Feel free to fork this repository and contribute to the project by submitting pull requests.

License
This project is open-source and available under the MIT License.

Contact
For any inquiries, please contact:

Shikhar Sharma
Email: sg7039@srmist.edu.in
GitHub: github.com/shikjazz
LinkedIn: linkedin.com/in/shikhar-sharma-275544227
