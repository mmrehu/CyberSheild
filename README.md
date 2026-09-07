# 🛡️ CyberShield

### Cyber Security Awareness System

> **Learn. Practice. Identify. Improve.**

CyberShield is a web-based **Cyber Security Awareness System** designed to help students, beginners, and general internet users understand common cybersecurity threats and develop safer digital habits through **interactive learning, simulated examples, quizzes, automatic scoring, and progress tracking**.

The project focuses on cybersecurity education rather than offensive security. It does **not** perform real-world attacks, credential harvesting, malware creation, or unauthorized penetration testing.

---

## 🚀 Overview

Cybersecurity awareness is increasingly important as users interact with online banking, social media, email, educational platforms, websites, and other digital services.

Many users know basic security terms but struggle to recognize threats in realistic situations.

CyberShield addresses this problem through an integrated learning experience:

```text
Learn
  ↓
Understand
  ↓
View Simulated Example
  ↓
Practice
  ↓
Take Quiz
  ↓
Receive Score
  ↓
Track Progress
```

Instead of simply presenting static cybersecurity information, CyberShield combines **education + practice + assessment** in a single web application.

---

## 🎯 Objectives

CyberShield aims to:

* 🔐 Improve basic cybersecurity awareness
* 🎣 Teach users how to identify phishing
* 🔑 Promote strong password practices
* 🛡️ Explain Multi-Factor Authentication (MFA)
* 🔗 Teach users to recognize suspicious links
* 🧠 Introduce social engineering concepts
* 📝 Provide interactive cybersecurity quizzes
* 📊 Automatically calculate quiz scores
* 📈 Track learning progress
* 👨‍💻 Provide an administrator panel for content management
* 🌐 Present cybersecurity concepts in simple language

---

## ✨ Key Features

### 👤 User Authentication

Users can:

* Register an account
* Log in securely
* Log out
* Access their personalized dashboard

Passwords should be stored using secure password hashing rather than plaintext storage.

---

### 📊 User Dashboard

The dashboard provides an overview of the user's learning activity.

It can display:

* Available modules
* Completed modules
* Quiz scores
* Overall learning progress

Example:

```text
┌─────────────────────────────────────┐
│           CYBERSHIELD               │
├─────────────────────────────────────┤
│ Welcome, User                       │
│                                     │
│ Modules Available        5          │
│ Modules Completed        3          │
│ Quiz Score               82%        │
│ Overall Progress         60%        │
└─────────────────────────────────────┘
```

---

### 📚 Cybersecurity Learning Modules

The initial learning structure includes:

```text
Cybersecurity Basics
        ↓
Phishing Awareness
        ↓
Password Security
        ↓
Multi-Factor Authentication
        ↓
Social Engineering
        ↓
Suspicious Links
```

Each module explains security concepts using beginner-friendly language.

---

### 🎣 Phishing Awareness

Users can examine **simulated security messages** and determine whether they appear safe or suspicious.

Example:

```text
┌─────────────────────────────────────┐
│       Example Security Message      │
│                                     │
│ "Your account needs verification."  │
│                                     │
│       [ SAFE ]  [ SUSPICIOUS ]      │
└─────────────────────────────────────┘
```

The purpose is to train users to identify warning signs without interacting with real malicious infrastructure.

---

### 🔑 Password Awareness

CyberShield teaches users about:

* Long passwords
* Unique passwords
* Password reuse risks
* Multi-Factor Authentication
* Password strength

A JavaScript-based password-strength demonstration can provide immediate feedback.

> **Important:** Passwords entered into a strength checker should not be stored.

---

### 📝 Interactive Quiz System

Users can answer cybersecurity questions and receive an automatically calculated score.

```text
Question
   ↓
Options
   ↓
User Answer
   ↓
Answer Verification
   ↓
Score Calculation
   ↓
Result
   ↓
Progress Update
```

Example:

**What should you do when you receive a suspicious link?**

* A. Click immediately
* B. Share it with friends
* C. Verify it before opening
* D. Enter your password

**Correct Answer: C**

---

### 📈 Progress Tracking

The system records learning activity and quiz performance.

Users can monitor:

* Completed lessons
* Quiz scores
* Total questions
* Percentages
* Overall progress

This allows users to understand where they are improving and where additional learning may be required.

---

### 👨‍💻 Administrator Panel

Administrators can manage the educational content.

#### Lesson Management

* Add lessons
* Edit lessons
* Delete lessons

#### Question Management

* Add quiz questions
* Edit questions
* Delete questions

#### User Management

* View users
* View user results

---

## 🏗️ System Architecture

```text
                    ┌──────────────┐
                    │     USER     │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │ WEB BROWSER  │
                    └──────┬───────┘
                           │
                           ▼
              ┌─────────────────────────┐
              │ HTML + Tailwind CSS     │
              │ JavaScript              │
              └────────────┬────────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │    APACHE    │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │     PHP      │
                    │ Application  │
                    │    Logic     │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │    MySQL     │
                    │   Database   │
                    └──────────────┘
```

---

## 🧩 Core Modules

| Module             | Purpose                           |
| ------------------ | --------------------------------- |
| Authentication     | Registration and login            |
| Dashboard          | User activity overview            |
| Learning           | Cybersecurity educational content |
| Phishing Awareness | Simulated threat identification   |
| Password Awareness | Password security education       |
| Quiz               | Knowledge assessment              |
| Score System       | Automatic score calculation       |
| Progress           | Learning progress tracking        |
| Admin Panel        | Content and user management       |

---

## 🗄️ Database Structure

CyberShield uses **MySQL** as its database.

### Users

```text
users
├── id
├── name
├── email
├── password
├── role
└── created_at
```

### Lessons

```text
lessons
├── id
├── title
├── category
├── content
└── created_at
```

### Questions

```text
questions
├── id
├── lesson_id
├── question
├── option_a
├── option_b
├── option_c
├── option_d
└── correct_answer
```

### Quiz Results

```text
quiz_results
├── id
├── user_id
├── score
├── total_questions
├── percentage
└── completed_at
```

### Progress

```text
progress
├── id
├── user_id
├── lesson_id
├── completed
└── completed_at
```

---

## 📁 Project Structure

```text
CyberShield/
│
├── index.php
├── login.php
├── register.php
├── logout.php
├── dashboard.php
│
├── config/
│   └── database.php
│
├── auth/
│   ├── login_process.php
│   └── register_process.php
│
├── lessons/
│   ├── index.php
│   ├── view.php
│   └── complete.php
│
├── quiz/
│   ├── index.php
│   ├── questions.php
│   ├── submit.php
│   └── result.php
│
├── progress/
│   └── index.php
│
├── admin/
│   ├── dashboard.php
│   ├── lessons.php
│   ├── questions.php
│   └── users.php
│
├── assets/
│   ├── css/
│   │   └── style.css
│   │
│   └── js/
│       └── main.js
│
└── database/
    └── cybershield.sql
```

---

## 🛠️ Technology Stack

| Layer               | Technology   |
| ------------------- | ------------ |
| Frontend            | HTML5        |
| UI Framework        | Tailwind CSS |
| Client-side Logic   | JavaScript   |
| Backend             | PHP          |
| Database            | MySQL        |
| Web Server          | Apache       |
| Local Environment   | XAMPP        |
| Database Management | phpMyAdmin   |
| Code Editor         | VS Code      |

---

## 💻 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/CyberShield.git
```

```bash
cd CyberShield
```

### 2. Install XAMPP

Install XAMPP with:

* Apache
* MySQL
* PHP
* phpMyAdmin

### 3. Move the Project

Copy the project into the XAMPP web directory:

```text
xampp/
└── htdocs/
    └── CyberShield/
```

### 4. Start Services

Open XAMPP Control Panel and start:

```text
Apache  → Start
MySQL   → Start
```

### 5. Create the Database

Open phpMyAdmin and create a database:

```text
cybershield
```

Import:

```text
database/cybershield.sql
```

### 6. Configure Database Connection

Update:

```text
config/database.php
```

with your local MySQL credentials.

Example:

```php
$host = "localhost";
$db   = "cybershield";
$user = "root";
$pass = "";
```

### 7. Run the Application

Open:

```text
http://localhost/CyberShield/
```

---

## 🔐 Security Considerations

CyberShield is an educational cybersecurity project, so security should also be considered in its implementation.

Recommended practices include:

* Password hashing
* Input validation
* Prepared SQL statements
* Session-based authentication
* Role-based access control
* Output escaping
* Protection against SQL injection
* Protection against XSS
* Secure session handling
* Server-side validation
* Proper authorization checks

### Password Security

Passwords must **never** be stored as plaintext.

Use PHP's password hashing functionality:

```php
password_hash($password, PASSWORD_DEFAULT);
```

For authentication:

```php
password_verify($password, $hash);
```

---

## 🧪 Testing

Testing should cover:

### Authentication

* Valid registration
* Duplicate email
* Invalid input
* Correct login
* Incorrect password
* Logout

### Learning Modules

* Lesson loading
* Lesson completion
* Progress updates

### Quiz System

* Correct answers
* Incorrect answers
* Score calculation
* Result storage
* Empty submissions
* Invalid question IDs

### Admin Panel

* Admin authentication
* Lesson CRUD operations
* Question CRUD operations
* User/result viewing
* Unauthorized access prevention

---

## ⚠️ Project Scope

CyberShield is designed specifically for **cybersecurity education and awareness**.

### ✅ Included

* Cybersecurity lessons
* Phishing awareness
* Password awareness
* MFA awareness
* Suspicious-link awareness
* Social engineering awareness
* Simulated examples
* Quizzes
* Score calculation
* Progress tracking
* Administration

### ❌ Not Included

* Real-world hacking
* Unauthorized penetration testing
* Malware creation
* Credential harvesting
* Password stealing
* Website attacks
* Real phishing campaigns
* Enterprise security monitoring
* Cybersecurity certification

---

## 🎓 Academic Project

CyberShield was developed as an undergraduate academic project focused on cybersecurity awareness and web application development.

### Team

| Member           | Registration No. |
| ---------------- | ---------------: |
| Rehu Talwar      |         12505449 |
| RadhaKanta Das   |         12510042 |
| Plan Saurosi     |         12515912 |
| Gareth Shamu     |         12502588 |
| Adroit Chigarire |         12508522 |

**Programme:** B.Sc. Computer Science – Cyber Security

**Project Date:** September 2026

---

## 📚 References

CyberShield's educational direction is informed by established cybersecurity resources including:

* **CISA** — Cybersecurity awareness and safe online practices
* **NIST** — Phishing awareness and human factors
* **OWASP** — Web application security awareness
* **PHP Documentation**
* **MySQL Documentation**
* **Tailwind CSS Documentation**

---

## 🔮 Future Improvements

Potential future improvements include:

* More cybersecurity learning modules
* Advanced phishing simulations
* Difficulty-based quizzes
* Achievement/badge system
* Leaderboards
* Personalized learning recommendations
* Detailed analytics dashboard
* Question randomization
* Certificate generation
* Accessibility improvements
* Responsive mobile-first improvements
* Expanded administrator controls
* More advanced progress analytics

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/new-feature
```

3. Commit your changes

```bash
git commit -m "Add new cybersecurity module"
```

4. Push the branch

```bash
git push origin feature/new-feature
```

5. Open a Pull Request

---

## ⚖️ Responsible Use

CyberShield is intended for **education, awareness, and authorized learning environments**.

The project must not be used to:

* Harvest credentials
* Conduct phishing attacks against real users
* Attack systems without authorization
* Deploy malware
* Perform unauthorized penetration testing

Always obtain appropriate authorization before conducting security testing.

---

## ⭐ Why CyberShield?

Traditional awareness:

```text
Read Information
      ↓
     Done
```

CyberShield:

```text
       LEARN
         ↓
     EXAMINE
         ↓
      PRACTICE
         ↓
        QUIZ
         ↓
       SCORE
         ↓
      PROGRESS
```

Cybersecurity awareness becomes more useful when users don't just **read about threats**, but also **practice recognizing them and measure what they have learned**.

---

<p align="center">

### 🛡️ CyberShield

**Cyber Security Awareness System**

**Learn • Practice • Identify • Improve**

</p>
