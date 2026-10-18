# YIC Student Feedback System

A web application where students at Yanbu Industrial College submit feedback on courses and campus services, and administrators review and manage it. Built by a team of two for **CS381 – Web Application Development**.

📄 **[Full project report](CS381_Report.pdf)** with wireframes, ER diagram, screenshots and code walkthrough.

## Features

**Students**
- Register, log in and log out
- Submit feedback with a subject and message
- View their own feedback and track its status: New, Reviewed or Resolved

**Administrators**
- View all feedback in a dashboard
- Update feedback status
- Delete feedback

**General**
- Role-based access: each role sees only its own pages
- Responsive design for mobile and desktop
- Client-side form validation in JavaScript

## Security

- **SQL injection prevention:** every query uses PDO prepared statements
- **Password hashing:** `password_hash()` and `password_verify()`
- **XSS protection:** user input is escaped with `htmlspecialchars()`
- **CSRF protection:** forms include a token that is checked on submit
- **Sessions:** protect pages and store the user's role

## Tech Stack

| Layer    | Technology                                  |
|----------|---------------------------------------------|
| Frontend | HTML5 (semantic), CSS3 (responsive), vanilla JavaScript |
| Backend  | PHP with sessions                           |
| Database | MySQL via PDO                               |
| Server   | Laragon / XAMPP                             |

No frameworks were used.

## Database

Two related tables:
- `users`: students and admins, with hashed passwords and a role
- `feedback`: subject, message, status and date, linked to `users` through `user_id`

## Running Locally

1. Start Laragon or XAMPP.
2. Import the SQL file from the `ph4` folder into MySQL.
3. Copy the `ph4` folder into `www` (Laragon) or `htdocs` (XAMPP).
4. Update the database settings in `db.php`.
5. Open `login.php` in the browser.

## Pages

| File                 | Purpose                               |
|----------------------|---------------------------------------|
| `login.php`          | Login with email and password         |
| `register.php`       | New account registration              |
| `home.php`           | Main page after login                 |
| `add_feedback.php`   | Submit feedback                       |
| `my_feedback.php`    | Student's own feedback and status     |
| `admin_feedback.php` | Admin dashboard to update and delete  |
| `logout.php`         | End the session                       |

## Team

Amjad Baali and Sarah Mohammed.

Original repository: [sarahmg1424-hash/project-CS381](https://github.com/sarahmg1424-hash/project-CS381)
