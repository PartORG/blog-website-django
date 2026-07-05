# Blog Website Django

A simple and scalable blog website built using Python and Django, designed for developers to create and manage dynamic web content.

## Requirements

- **Python**: 3.8+
- **Django**: 4.0+
- **PostgreSQL**: 13+

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

## Usage

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

## Contributing

We welcome contributions to enhance the functionality of our blog website. To contribute:

1. Fork the repository.
2. Create a new branch for your feature: `git checkout -b feature/YourFeatureName`.
3. Commit your changes: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin feature/YourFeatureName`.
5. Open a pull request detailing your changes.