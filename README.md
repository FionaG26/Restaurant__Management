# Restaurant Management System

A web-based application for managing restaurant operations, including menu management, order processing, and customer interactions.

## Features

- User Registration and Authentication
- Role-based Access Control
- Restaurant and Branch Management
- Menu Item Management
- Order Placement and Management
- Order Rating System

## Prerequisites

- Python 3
- Django
- PostgreSQL

## Installation

### Step 1: Install PostgreSQL

#### Ubuntu

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```

#### macOS

```bash
brew update
brew install postgresql
brew services start postgresql
```

#### Windows

1. Download the installer from the [PostgreSQL official website](https://www.postgresql.org/download/).
2. Run the installer and follow the setup instructions.

### Step 2: Create Database and User

```bash
sudo -i -u postgres
psql
CREATE DATABASE restaurant_management_db;
CREATE USER restaurant_user WITH PASSWORD 'your_password';
GRANT ALL PRIVILEGES ON DATABASE restaurant_management_db TO restaurant_user;
\q
exit
```

### Step 3: Configure Django

Install `psycopg2`:

```bash
pip install psycopg2-binary
```

Update `settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'restaurant_management_db',
        'USER': 'restaurant_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

### Step 4: Start Django Project

```bash
django-admin startproject restaurant_management_system
cd restaurant_management_system
python manage.py startapp orders
```

### Step 5: Create Models

Define your models in `orders/models.py`.

### Step 6: Apply Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 7: Create Superuser

```bash
python manage.py createsuperuser
```

### Step 8: Register Models in Admin

Register your models in `orders/admin.py`.

### Step 9: Run Server

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` in your web browser.
