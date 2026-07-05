# Blog Website Django

A simple and scalable blog website built using Python and Django, designed for developers to create and manage dynamic web content.

## Table of Contents
1. [Features](#features)
2. [How It Works](#how-it-works)
3. [Technology Stack](#technology-stack)
4. [Requirements](#requirements)
5. [Installation](#installation)
6. [Configuration](#configuration)
7. [Quick Start](#quick-start)
8. [Usage](#usage)
9. [Project Structure](#project-structure)
10. [Development](#development)
11. [Testing](#testing)
12. [Limitations](#limitations)
13. [License](#license)

## Features

### User Authentication
- **What it does:** Manages user registration, login, and logout.
- **Why it exists:** Ensures secure access to the blog content.
- **Why it is useful:** Protects sensitive information and allows for personalized experiences.

### Blog Article Management
- **What it does:** Allows users to create, edit, and delete blog articles.
- **Why it exists:** Enables dynamic content creation without manual intervention.
- **Why it is useful:** Facilitates a content management system (CMS) for the blog.

## How It Works

The project follows a typical Django application structure. The `djangonautic` app contains the main settings and views, while `accounts` and `articles` handle user authentication and blog article management, respectively.

### Architecture Diagram
```
+-------------------+
|   djangonautic    |
|  (Main App)       |
+---------+---------+
          |
          v
+---------+---------+
|   accounts      |
|  (Auth)         |
+---------+---------+
          |
          v
+---------+---------+
|   articles      |
|  (Blog)         |
+-------------------+
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Python     | Backend programming language. |
| Django     | Web framework for building scalable web applications. |
| PostgreSQL | Relational database management system. |
| Bootstrap  | Frontend framework for responsive design. |

## Requirements

- **Python:** 3.8+
- **Django:** 4.0+
- **PostgreSQL:** 13+

## Installation

### Clone the Repository
```bash
git clone https://github.com/PartORG/blog-website-django.git
cd blog-website-django
```

### Create and Activate Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

### Environment Setup
Create a `.env` file in the root directory and configure it according to your PostgreSQL setup:
```env
DATABASE_NAME='your_database'
DATABASE_USER='your_user'
DATABASE_PASSWORD='your_password'
DATABASE_HOST='localhost'
DATABASE_PORT='5432'
```

### Run Migrations
```bash
python manage.py migrate
```

### Start the Development Server
```bash
python manage.py runserver
```

## Configuration

The project uses environment variables for database configuration. Ensure you have a `.env` file with the following content:
```env
DATABASE_NAME='your_database'
DATABASE_USER='your_user'
DATABASE_PASSWORD='your_password'
DATABASE_HOST='localhost'
DATABASE_PORT='5432'
```

## Quick Start

To create a new blog post, use Django's admin interface or write a script to interact with the API:

### Using Django Admin Interface
1. Navigate to `http://localhost:8000/admin`.
2. Log in using your credentials.
3. Go to "Articles" and click "Add Article".
4. Fill in the details and save.

### Using API
```python
import requests

# Create a new blog post via API
response = requests.post('http://localhost:8000/api/posts/', json={
    'title': 'My First Post',
    'content': 'This is the content of my first blog post.'
}, auth=('username', 'password'))

if response.status_code == 201:
    print("Post created successfully!")
else:
    print("Failed to create post.")
```

## Usage

To interact with the blog website, you can use Django's admin interface or write scripts to manage articles and users.

### Example Commands
```bash
# List all blog posts
python manage.py shell
>>> from articles.models import Article
>>> Article.objects.all()
```

## Project Structure

```plaintext
blog-website-django/
│
├── accounts/                 # User authentication and management
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations/
│   │   └── __init__.py
│   ├── models.py
│   ├── templates/accounts/
│   │   ├── login.html
│   │   ├── logout.html
│   │   └── signup.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── articles/               # Blog article management
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── migrations/
│   │   ├── 0001_initial.py
│   │   ├── 0002_article_thumb.py
│   │   └── 0003_article_author.py
│   ├── models.py
│   ├── templates/articles/
│   │   ├── article_create.html
│   │   ├── article_detail.html
│   │   └── article_list.html
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── assets/                   # Static files
│   ├── 1.jpg
│   ├── logo.jpg
│   ├── slugify.js
│   └── styles.css
├── djangonautic/             # Main project settings and views
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── views.py
├── manage.py                 # Django command-line utility
└── requirements.txt          # Python dependencies
```

## Development

The development workflow involves setting up a virtual environment, installing dependencies, and running migrations. The project uses Django's built-in admin interface for managing users and articles.

## Testing

Testing is not available in this repository as indicated by the analysis.

## Limitations

- **No testing:** The project lacks automated tests.
- **Basic authentication:** Uses simple username/password authentication without OAuth or JWT.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.