# Hospital Management System (Django)

A web-based hospital management system built with Python, Django and MySQL. It has three role-based panels for **Admin**, **Doctor** and **Patient**, and covers doctor registration, patient records, appointment booking and medical history.

## Features

**Admin**
- Manage doctor specializations
- View and manage registered doctors and patients
- See each doctor's appointments and patients
- Search doctors and generate reports for a date range
- Edit the public website's About and Contact details

**Doctor**
- Sign up and manage a profile
- Add and manage patients, and record medical history (blood pressure, weight, blood sugar, temperature, prescription)
- Approve, cancel and complete appointments, and add remarks and prescriptions
- Search appointments and patients, and generate reports for a date range

**Patient**
- Register and log in
- Book appointments with a doctor by specialization
- View appointment history and details, and cancel appointments

**General**
- Custom user model with role-based access for Admin, Doctor and Patient
- Profile update and password change for all users
- Secrets and database settings loaded from a `.env` file

## Tech stack

- **Backend:** Python 3.13, Django 5.2
- **Database:** MySQL
- **Frontend:** Django templates, HTML, CSS, Bootstrap

## Project structure

```
Hospital-Management-System-Django-Project/hms/hospital/
├── docappsystem/   # Project settings, URLs, and admin/doctor/patient views
├── dasapp/         # Models: users, doctors, patients, appointments, medical history
├── templates/      # HTML templates for each panel
├── static/         # CSS, JavaScript and images
├── manage.py
├── requirements.txt
└── .env.example    # Template for local settings
```

## Running it locally

**Requirements:** Python 3.11+ and MySQL.

1. **Clone the repository**
   ```bash
   git clone https://github.com/abdulrehmanprojects/hospital-management-system.git
   cd hospital-management-system/Hospital-Management-System-Django-Project/hms/hospital
   ```

2. **Create a virtual environment and install packages**
   ```bash
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # macOS/Linux
   pip install -r requirements.txt
   ```

3. **Create the database.** In MySQL:
   ```sql
   CREATE DATABASE hmspythondb;
   ```

4. **Set up your local settings.** Copy `.env.example` to `.env`, then set your own `SECRET_KEY` and MySQL password.

5. **Create the tables and an admin account**
   ```bash
   python manage.py migrate
   python manage.py createsuperuser
   ```

6. **Run the server**
   ```bash
   python manage.py runserver
   ```
   Then open http://127.0.0.1:8000.

## Credits

This project is based on an open-source Django hospital/doctor appointment system. The website front end uses the free **Novena** template by [Themefisher](https://themefisher.com).

**My changes:**
- Moved the secret key and database settings to environment variables (`.env`)
- Cleaned up the project structure and added `requirements.txt` and `.gitignore`
- Wrote setup documentation

## Planned improvements

- REST API with Django REST Framework
- JWT authentication for the API
- Automated tests
- Docker setup
