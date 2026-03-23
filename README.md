# 🔐 Django Auth Project

A clean Django authentication web app built with Python & Django.

## 🌐 Live Demo
> **[👉 Click here to open the app](https://smit-djangoproject.up.railway.app)**

---

## ✅ Features
- User Registration
- User Login / Logout
- Protected Dashboard
- Plain CSS Styling

## 🛠️ Tech Stack
- Python 3.11
- Django 4.2
- WhiteNoise
- Gunicorn
- Railway (Deployment)

## 📁 Project Structure
```
├── accounts/        # Auth logic
├── templates/       # HTML pages
├── static/          # CSS styles
├── manage.py
└── requirements.txt
```

## ⚙️ Local Setup
```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
