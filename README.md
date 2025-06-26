# 🏥 Healthcare Backend API

A secure RESTful backend system for managing **patients**, **doctors**, and their assignments, built using **Django**, **Django REST Framework**, **PostgreSQL**, and **JWT Authentication**.

---

## 🚀 Features

- ✅ User registration & login using JWT
- ✅ Secure patient and doctor management
- ✅ Assign multiple doctors to patients
- ✅ PostgreSQL database integration
- ✅ Auth-protected API access
- ✅ `.env` support via `python-decouple`

---

## Tech Stack

- Python 3.x
- Django 5.x
- Django REST Framework
- PostgreSQL
- Simple JWT (`djangorestframework-simplejwt`)
- python-decouple (for environment variables)

---

## ⚙️ Setup Instructions

### 1. Clone the repository


git clone https://github.com/nallurisaisreedhar-4241/healthcare-backend
cd healthcare-backend

2. Create and activate a virtual environment

python -m venv myenv
myenv\Scripts\activate   # For Windows

3. Install required packages

pip install -r requirements.txt

4. Create .env file
In the project root, create a .env file:

DB_NAME=healthcare_db
DB_USER=postgres
DB_PASSWORD=your_postgres_password
DB_HOST=localhost
DB_PORT=5432
SECRET_KEY=your_django_secret_key

5. Apply migrations

python manage.py makemigrations
python manage.py migrate

6. Create a superuser (optional)

python manage.py createsuperuser

7. Run the server

python manage.py runserver
🔐 Authentication
This backend uses JWT for user authentication.

🔑 Auth Endpoints:
POST /api/auth/register/ – Register a new user

POST /api/auth/login/ – Login and get JWT tokens

POST /api/auth/token/refresh/ – Refresh access token

📌 Use the access token from the login API in your headers:


Authorization: Bearer <access_token>
📬 API Endpoints
👤 Auth
POST /api/auth/register/

POST /api/auth/login/

POST /api/auth/token/refresh/

🧑‍⚕️ Patients
POST /api/patients/

GET /api/patients/

GET /api/patients/<id>/

PUT /api/patients/<id>/

DELETE /api/patients/<id>/

👨‍⚕️ Doctors
POST /api/doctors/

GET /api/doctors/

GET /api/doctors/<id>/

PUT /api/doctors/<id>/

DELETE /api/doctors/<id>/

🔁 Patient–Doctor Mapping
POST /api/mappings/
Assign a doctor to a patient

GET /api/mappings/
List all mappings

GET /api/mappings/<patient_id>/
Get all doctors for a specific patient

DELETE /api/mappings/delete/<mapping_id>/
Remove a doctor from a patient

📂 Project Structure

healthcare/
├── api/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
├── healthcare/
│   ├── settings.py
│   ├── urls.py
├── manage.py
├── .env
├── requirements.txt
├── README.md
🧪 Testing
Use Postman to test the endpoints with JWT tokens in the Authorization header.

📦 Generate requirements.txt
If needed:


pip freeze > requirements.txt
📌 Notes
Data is stored in PostgreSQL and can be viewed using pgAdmin.

Use the Django admin panel (/admin) to manually inspect data if needed.
