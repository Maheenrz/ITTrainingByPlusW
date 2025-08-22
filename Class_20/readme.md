## 🌍 Class 20 – Deploy Django Blog on AWS EC2

### Steps I did
1. Launched an **EC2 instance** (Ubuntu).
2. Installed dependencies:
   ```bash
   sudo apt update
   sudo apt install python3-pip python3-venv git
````

3. Cloned my Django project:

   ```bash
    git clone <repo-url> django-blog
    cd django-blog
```

4. Created & activated virtual environment:

   ```bash
   python3 -m venv env
   source env/bin/activate
   ```
5. Installed Django:

   ```bash
   pip install django
   ```
6. Ran the server:

   ```bash
   python3 manage.py runserver 0.0.0.0:8000
   ```
7. Opened app in browser:
   `http://<3.25.60.191>:8000`


✅ Blog was successfully accessible from EC2 instance.

---
