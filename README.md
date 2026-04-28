# Online Course - IBM Django Final Project

[Ver en espanol](README_es.md)

This repository contains my version of the final project for IBM's **Django Application Development with SQL and Databases** course. The original exercise is based on material provided by **IBM Developer Skills Network**, and this repository includes my own implementation and adaptation of that final project.

The application is a simple online course platform built with Django. Users can register, log in, browse courses, enroll in them, read course lessons, and complete a small quiz associated with each course.

## Context

This project is not intended to be a full e-learning platform. It is an academic practice project focused on reinforcing Django and database concepts:

- Data modeling with the Django ORM.
- Relationships between users, courses, lessons, enrollments, questions, choices, and submissions.
- Class-based views and function-based views.
- Basic forms with Django templates.
- Content management through the Django admin.
- SQLite persistence for local development.
- Basic deployment preparation with Gunicorn and Cloud Foundry.

## Main Features

- Course listing.
- User registration, login, and logout.
- Enrollment for authenticated users.
- Course detail page with lessons.
- Course quiz with questions and answer choices.
- Submission tracking through the `Submission` model.
- Score calculation by comparing selected answers with the correct choices.
- Admin management for courses, lessons, instructors, learners, questions, choices, and submissions.

## Project Structure

```text
.
|-- manage.py
|-- myproject/              # Main Django project configuration
|-- onlinecourse/           # Main course application
|   |-- models.py           # Domain models
|   |-- views.py            # Course, user, quiz, and result views
|   |-- urls.py             # App routes
|   |-- admin.py            # Django admin configuration
|   `-- templates/          # Bootstrap-based HTML templates
|-- static/                 # Static files and course assets
|-- images/                 # Screenshots used in the documentation
|-- requirements.txt
|-- Procfile
|-- manifest.yml
`-- runtime.txt
```

## Screenshots

The following screenshots were taken by me to document the current state of the application and are included in this repository.

Initial menu with the course list:

<img src="images/home.png" alt="Initial menu with course list" width="520">

Course page with the quiz expanded:

<img src="images/course.png" alt="Course page with quiz" width="520">

## Main Models

The `onlinecourse` app defines the main domain models:

- `Course`: course name, description, image, publication date, and instructors.
- `Lesson`: content associated with a course.
- `Enrollment`: relationship between a user and a course.
- `Question`: question associated with a course.
- `Choice`: possible answer for a question, including whether it is correct.
- `Submission`: quiz submission with the selected choices.
- `Instructor` and `Learner`: profiles linked to Django users.

## Running Locally

1. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Apply migrations:

```bash
python manage.py migrate
```

4. Create a superuser to manage courses and questions through the admin:

```bash
python manage.py createsuperuser
```

5. Start the development server:

```bash
python manage.py runserver
```

The application will be available at:

```text
http://127.0.0.1:8000/onlinecourse/
```

The admin panel will be available at:

```text
http://127.0.0.1:8000/admin/
```

## IBM and Authorship Notes

This repository comes from a fork/base project used in the IBM Developer Skills Network course. Its purpose is educational, and the development included here represents my own work and adaptation of the final project for **Django Application Development with SQL and Databases**.

The IBM reference is kept because the original assignment, starter structure, and part of the resources belong to the course context.

## Project Status

Academic project completed as Django practice. It can be used as a simple reference for connecting models, views, templates, and SQL relationships in a basic web application.
