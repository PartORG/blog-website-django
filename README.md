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
11. [License](#license)

## Features

### User Authentication and Management (accounts)
- **What it does:** Manages user accounts, including registration, login, and logout.
- **Why it exists:** Ensures secure access to the blog platform.
- **Why it is useful:** Protects content and allows for personalized experiences.

### Blog Article Management (articles)
- **What it does:** Enables users to create, edit, and delete blog articles.
- **Why it exists:** Facilitates content creation and management.
- **Why it is useful:** Provides a platform for sharing knowledge and ideas.

## How It Works

The project is built using Python and Django, with a focus on scalability. It includes user accounts, blog articles, and static assets. The development environment requires Python 3.8+, Django 4.0+, and PostgreSQL 13+.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| **Python** | Programming language for backend logic. |
| **Django** | Web framework for building scalable web applications. |
| **PostgreSQL** | Relational database management system for data storage. |

## Requirements

- **Python:** 3.8+
- **Django:** 4.0+
- **PostgreSQL:** 13+

## Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/PartORG/blog-website-django.git
   cd blog-website-django
   ```

2. **Create and Activate Virtual Environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Setup:**

   Create a `.env` file in the root directory and configure it according to your PostgreSQL setup:

   ```env
   DATABASE_NAME='your_database'
   DATABASE_USER='your_user'
   DATABASE_PASSWORD='your_password'
   DATABASE_HOST='localhost'
   DATABASE_PORT='5432'
   ```

5. **Run Migrations:**

   ```bash
   python manage.py migrate
   ```

6. **Start the Development Server:**

   ```bash
   python manage.py runserver
   ```

## Configuration

The project uses environment variables for database configuration. Ensure you have a `.env` file with the following settings:

```env
DATABASE_NAME='your_database'
DATABASE_USER='your_user'
DATABASE_PASSWORD='your_password'
DATABASE_HOST='localhost'
DATABASE_PORT='5432'
```

## Quick Start

To create a new blog post, you can use Django's admin interface or write a script to interact with the API:

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

To interact with the blog website, you can use Django's admin interface or write scripts to manage content programmatically.

### Admin Interface
- Navigate to `http://localhost:8000/admin` and log in using your credentials.
- Manage users and articles from the admin panel.

### API Endpoints
- **Create a Post:** `POST /api/posts/`
  - Example:
    ```json
    {
      "title": "My First Post",
      "content": "This is the content of my first blog post."
    }
    ```
- **Retrieve Posts:** `GET /api/posts/`

## Project Structure

```plaintext
blog-website-django/
│
├── accounts/                 # User authentication and management
├── articles/               # Blog article management
├── assets/                   # Static files
├── djangonautic/             # Main project settings and views
├── manage.py                 # Django command-line utility
└── requirements.txt          # Python dependencies
```

## Development

The development workflow involves setting up a virtual environment, installing dependencies, running migrations, and starting the development server.

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/PartORG/blog-website-django.git
   cd blog-website-django
   ```

2. **Create and Activate Virtual Environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run Migrations:**

   ```bash
   python manage.py migrate
   ```

5. **Start the Development Server:**

   ```bash
   python manage.py runserver
   ```

## Testing

Testing is not available for this project.

## Limitations

- The project does not include advanced features like user roles and permissions.
- No automated testing is provided.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.