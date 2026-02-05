# Django Blog Deployment on AWS EC2

This project demonstrates how to deploy a Django application on an **AWS EC2 Ubuntu instance** using **Gunicorn** as the WSGI server.

---

## 📌 Steps Performed

### 1. Launch EC2 Instance

* Launched an **Ubuntu 24.04 LTS** t2.micro instance.
* Configured **security group** to allow:

  * SSH (22)
  * HTTP (80)
  * Custom TCP (8000) for testing

---

### 2. Write Deployment Script (`deploy.sh`)

A bash script was created to **automate deployment**. It:

1. Installs system packages (`python3`, `pip`, `venv`, `git`, `nginx`).
2. Removes any old code.
3. Clones the project from GitHub.
4. Sets up a virtual environment.
5. Installs Python dependencies + Gunicorn.
6. Ensures `STATIC_ROOT` exists in Django settings.
7. Runs migrations + collects static files.
8. Starts the app with **Gunicorn**.

Run script with:

```bash
chmod +x deploy.sh
./deploy.sh
```

---

### 3. Configure Django

* Edited **`blog/settings.py`**:

```python
ALLOWED_HOSTS = ["3.106.246.184", "localhost", "127.0.0.1"]
STATIC_ROOT = BASE_DIR / "staticfiles"
```

---

### 4. Run Application

Start server manually:

```bash
cd ~/django-blog
source venv/bin/activate
venv/bin/gunicorn --bind 0.0.0.0:8000 blog.wsgi
```

Visit in browser:
👉 `http://3.106.246.184:8000`

---

## ⚠️ Issues Faced & Fixes

1. **Gunicorn not found** → Installed inside virtual environment.
2. **Static files error** → Added `STATIC_ROOT`.
3. **DisallowedHost error** → Added EC2 public IP to `ALLOWED_HOSTS`.

---

## 📂 Project Structure

```
django-blog/
│── blog/          # Django project
│── posts/         # App
│── templates/     # HTML files
│── manage.py
│── requirements.txt
│── venv/          # Virtual environment
│── deploy.sh      # Deployment script
```

---


