<<<<<<< HEAD

# 🚀 Django + Wagtail + React + Bootstrap Project Setup Guide

This guide details each step taken to set up a robust, full-stack web application using Django + Wagtail (backend/CMS), and React + Bootstrap (frontend).

---

## 1. Environment Preparation

**What:**
Create an isolated Python and Node.js environment for your project.

**Why:**
Prevents dependency conflicts, ensures your setup matches production, and avoids “works on my machine” issues.

**How:**

1. **Install [Anaconda/Miniconda](https://docs.conda.io/en/latest/miniconda.html)** if not already.
2. **Create and activate your Conda environment:**

   ```bash
   conda env create -f environment.yml  # (environment.yml lists python=3.11, pip, nodejs)
   conda activate drw-temp2
   ```

3. **Verify versions:**

   ```bash
   python --version
   node --version
   npm --version
   ```

   You should see Python 3.11.x, Node 22.x, npm 10.x.

---

## 2. Initialize Git Version Control

**What:**
Set up Git for tracking project changes.

**Why:**
Enables you to roll back mistakes, safely collaborate, and prepares for future cloud deployment.

**How:**

1. **Initialize git:**

   ```bash
   git init
   ```

2. **Add a `.gitignore` file** to the project root, to keep your repo clean (ignore Python/Node/Conda/system files):

   ```gitignore
   # Python
   __pycache__/
   *.py[cod]
   *.sqlite3
   *.env
   .env*
   .venv/
   .DS_Store

   # Conda
   .conda/
   .env/
   env/
   .mypy_cache/

   # Node
   node_modules/
   npm-debug.log
   yarn-debug.log
   yarn-error.log

   # OS
   Thumbs.db
   .idea/
   .vscode/

   # Misc
   *.log
   *.pot
   *.mo
   *.pyc
   *.pyo
   ```

3. **First commit:**

   ```bash
   git add .
   git commit -m "Initial project setup: Conda env, README, .gitignore"
   ```

---

## 3. Backend Setup: Django + Wagtail

**What:**
Install Django and Wagtail and initialize your backend structure.

**Why:**
Django is your backend web framework. Wagtail adds a powerful CMS for content management.

**How:**

1. **Install Django and Wagtail:**

   ```bash
   pip install django
   pip install wagtail
   ```

2. **Start a new Django project in your current directory** (good practice when using a separate frontend):

   ```bash
   django-admin startproject backend .
   ```

   _The `.` puts files in the current folder rather than creating a new subfolder. If you want the backend isolated, use `django-admin startproject backend` instead._

3. **Initialize a Wagtail CMS project inside your backend folder:**

   ```bash
   wagtail start mysite backend
   ```

   _Change `mysite` to another name if desired._

4. **Install PostgreSQL adapter for production DB use:**

   ```bash
   pip install psycopg2-binary
   ```

---

## ✅ What’s Done So Far

- Isolated Python/Node environment using Conda
- Initialized Git version control
- Added proper `.gitignore`
- Installed Django & Wagtail and started backend project structure

---

## 🔜 Next Steps

- Set up your database and migrate initial models
- Create Django superuser/admin
- Run the backend server to verify install
- (Afterward: move to React frontend and API integration)

---

**Tip:**
After each major step, commit your changes in Git to keep your project history clear!




## 4. Database Migration & Admin User Setup

**What:**  
Apply Django’s database migrations and create a superuser for admin access.

**Why:**  
Migrations create the tables Django and Wagtail need to function. A superuser lets you log into Django and Wagtail admin panels to manage your site.

**How:**

1. **Migrate the database** (run inside the `backend` folder):
    ```bash
    cd backend
    python manage.py migrate
    ```

2. **Create an admin (superuser) account:**
    ```bash
    python manage.py createsuperuser
    ```
    Follow the prompts for username, email, and password.

3. **Run the development server:**
    ```bash
    python manage.py runserver
    ```
    - Open [http://localhost:8000/admin](http://localhost:8000/admin) to access Django admin.
    - Log in with your new superuser account.

---

## ✅ Status So Far

- Environment & dependencies set up with Conda
- Git repo initialized
- Backend scaffolded (Django + Wagtail)
- Database migrated, admin user created
- Local server up and running!

---
````

---

## **Git Commit and Push to GitHub**

Now, save your progress and publish it to your GitHub repo.

**A. Add, Commit, and Push:**

From your project root (outside the `backend` folder):

```bash
git add .
git commit -m "🛠 Backend setup: Django+Wagtail, initial migration, superuser, updated README"
git branch -M main
git remote add origin https://github.com/Aryan1359/Django-Wagtail-CMS-Base-Template.git
git push -u origin main
```

> * If you already set the remote before, you may get an error. If so, run:
>
>   ```
>   git remote set-url origin https://github.com/Aryan1359/Django-Wagtail-CMS-Base-Template.git
>   git push -u origin main
>   ```

---

**When you’re done, reply "pushed!" and I’ll help you move to the next step: customizing Wagtail (home page, StreamField, etc.) or setting up the React frontend.**
If you hit any git errors, just paste the message here!
=======
# Django-Wagtail-CMS-Base-Template
Django-Wagtail-CMS-Base Template Created and ready for further development
>>>>>>> 24bcaba0bca5525b7790513514409be99bdb9809
