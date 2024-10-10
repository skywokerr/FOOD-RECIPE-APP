
# 🍽️ Food Recipe App

This project is a fully-featured **Food Recipe App** built using Django, which includes user authentication, full CRUD (Create, Read, Update, Delete) functionalities for managing recipes, and can be deployed for live production on **Heroku**.

## 🛠️ Features

- **User Authentication**: 
  - Users can sign up, log in, and log out.
  - Password hashing for security.
  - Users can reset their password via email.
  
- **Recipe Management (CRUD)**:
  - **Create**: Users can create new food recipes.
  - **Read**: Users can view the recipes created by all users.
  - **Update**: Users can edit recipes they created.
  - **Delete**: Users can delete recipes they created.
  
- **Recipe Categories**: Users can filter recipes by categories (e.g., breakfast, lunch, dinner).
  
- **Recipe Details**: Each recipe contains detailed information including ingredients, preparation steps, and optional images.

- **User Profile**: Users can manage their profile, view their saved recipes, and track their recipe creation history.

- **Responsive Design**: Fully responsive and mobile-friendly UI for seamless browsing on any device.

## 📦 Technologies Used

- **Backend**: Django (Python) / Flask / Node.js
- **Frontend**: HTML, CSS 
- **Database**: PostgreSQL (for production) and SQLite (for local development) # I used SQLite
- **Deployment**: Heroku (for live production deployment) # Deploy it on Heroku 
- **Authentication**: Django's built-in authentication
- **Heroku Add-ons**: PostgreSQL, SendGrid (for email notifications, password reset) # I used the default SMTP, you can tune it to your liking.

## 📑 Prerequisites

To run this project locally, you will need:

- **Python 3.x** installed on your machine.
- **Git** for version control.
- **PostgreSQL** for production (optional for local testing).
- **Heroku CLI** to manage deployment.

### Optional Setup

- **pipenv** or **virtualenv** for managing virtual environments.
- **Docker** for containerized development and deployment (if applicable).

## 🚀 Getting Started

To get a local copy up and running, follow these steps:

### 1. Clone the repository:

```bash
git clone https://github.com/skywokerr/food-recipe-app.git
cd food-recipe-app
```

### 2. Create and activate a virtual environment:

For **pipenv**:
```bash
pipenv install
pipenv shell
```

For **virtualenv**:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

### 3. Install the project dependencies:

```bash
pip install -r requirements.txt
```

### 4. Configure the Database:

- In the root of the project, create a `.env` file for environment variables:

```env
SECRET_KEY=your-secret-key
DEBUG=True
DATABASE_URL=postgres://your-db-url (optional for local dev)
EMAIL_HOST_USER=your-email@example.com
EMAIL_HOST_PASSWORD=your-email-password
```

- For **local development**, you can use **SQLite** (default in Django). For production, configure **PostgreSQL** as your database.

### 5. Run Database Migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create a Superuser:

```bash
python manage.py createsuperuser
```

### 7. Start the Development Server:

```bash
python manage.py runserver
```

The app will be running locally at `http://127.0.0.1:8000/`.

## 🛠️ Deployment to Heroku

To deploy the app to **Heroku**, follow these steps:

### 1. Create a Heroku App:

```bash
heroku create your-app-name
```

### 2. Add Heroku PostgreSQL:

```bash
heroku addons:create heroku-postgresql:hobby-dev
```

### 3. Set Environment Variables:

```bash
heroku config:set SECRET_KEY=your-secret-key
heroku config:set DEBUG=False
```

### 4. Deploy the app:

```bash
git push heroku master
```

### 5. Run Migrations on Heroku:

```bash
heroku run python manage.py migrate
```

### 6. Create a Superuser on Heroku:

```bash
heroku run python manage.py createsuperuser
```

Now, your app is deployed and live!

## 🧪 Running Tests

To run the test suite for the project:

```bash
python manage.py test
```

## 🔧 Troubleshooting

### Common Issues:

- **App Crash on Heroku**: Ensure that your environment variables are correctly set on Heroku (`SECRET_KEY`, `DATABASE_URL`, etc.).
- **Static Files Issue**: Run `python manage.py collectstatic` before deployment and make sure Heroku’s `whitenoise` is configured for static file handling.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## ✨ Acknowledgements

- [Django Documentation](https://docs.djangoproject.com/en/stable/)
- [Heroku Documentation](https://devcenter.heroku.com/)

---

