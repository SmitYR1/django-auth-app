# Django Auth Project

A clean academic Django authentication project with Login, Register, Dashboard, and Logout functionality.

---

## 📁 Project Structure

```
django_auth_project/
├── accounts/
│   ├── __init__.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
├── django_auth_project/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── static/
│   └── css/
│       └── style.css
├── templates/
│   └── registration/
│       ├── login.html
│       ├── register.html
│       └── dashboard.html
├── manage.py
├── requirements.txt
├── Procfile
└── README.md
```

---

## ⚙️ Local Setup

### 1. Create & activate virtual environment
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run migrations
```bash
python manage.py migrate
```

### 4. (Optional) Create superuser
```bash
python manage.py createsuperuser
```

### 5. Collect static files
```bash
python manage.py collectstatic
```

### 6. Run the server
```bash
python manage.py runserver
```

Visit: http://127.0.0.1:8000/

---

## 🌐 Pages / Routes

| URL          | Page       | Auth Required |
|--------------|------------|---------------|
| `/`          | Login      | No            |
| `/login/`    | Login      | No            |
| `/register/` | Register   | No            |
| `/dashboard/`| Dashboard  | ✅ Yes        |
| `/logout/`   | Logout     | ✅ Yes        |
| `/admin/`    | Admin Panel| Superuser     |

---

## ☁️ Cloud Deployment

### AWS Elastic Beanstalk
1. Install EB CLI: `pip install awsebcli`
2. Initialize: `eb init -p python-3.11 django-auth-app`
3. Create environment: `eb create django-auth-env`
4. Set env variables:
   ```bash
   eb setenv SECRET_KEY=your-secret-key DEBUG=False
   ```
5. Deploy: `eb deploy`

### GCP App Engine
1. Create `app.yaml`:
   ```yaml
   runtime: python311
   entrypoint: gunicorn -b :$PORT django_auth_project.wsgi
   env_variables:
     SECRET_KEY: "your-secret-key"
     DEBUG: "False"
   ```
2. Deploy: `gcloud app deploy`

### Azure App Service
1. Install Azure CLI and login: `az login`
2. Create web app:
   ```bash
   az webapp up --name django-auth-app --runtime PYTHON:3.11
   ```
3. Set env vars in Azure Portal → Configuration → Application Settings

---

## 🔐 Environment Variables (Production)

| Variable     | Description                      |
|--------------|----------------------------------|
| `SECRET_KEY` | Django secret key (keep private!)|
| `DEBUG`      | Set to `False` in production     |

---

## 🛠️ Tech Stack

- Python 3.11+
- Django 4.2
- WhiteNoise (static files)
- Gunicorn (WSGI server)
- SQLite (local) / PostgreSQL (recommended for production)
