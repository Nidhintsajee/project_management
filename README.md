# Project Management Application
This is a Django-based Project Management API that provides functionalities for managing projects, tasks, and users. This API includes user registration, login, and project and task management with JWT authentication.

## Prerequisites
Before setting up the project, make sure you have the following installed:

* Python (3.10.12 recommended)
* Django (5.1.2 recommended)
* PostgreSQL (optional, if you wish to use a different database than SQLite)
* Git
## Project Setup
### 1. Clone the Repository
Clone the project repository to your local machine:

git clone https://github.com/Nidhintsajee/project_management.git
cd project-management-app
### 2. Create and Activate a Virtual Environment
Create a virtual environment to isolate the project dependencies:

python3 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
### 3. Install Dependencies
Install the necessary packages using pip:

pip install -r requirements.txt
Note: Ensure that requirements.txt includes packages like Django, djangorestframework, and djangorestframework-simplejwt.

### 4. Configure Environment Variables
Create a .env file to store environment variables. Here’s an example of what your .env file should contain:

SECRET_KEY=your_secret_key
DEBUG=True
DATABASE_URL=sqlite:///db.sqlite3  # Use your preferred database configuration
Update settings.py to load the environment variables as needed.

### 5. Migrate the Database
Run the database migrations to set up the necessary tables:


python manage.py migrate
### 6. Create a Superuser (Admin)
To access the Django Admin and manage data directly, create a superuser:


python manage.py createsuperuser
### 7. Run the Server
Start the Django development server:


python manage.py runserver
The API should now be accessible at http://127.0.0.1:8000/.

## API Endpoints
The main API endpoints include:

### User Management
* Register: POST /api/users/register/
* Login: POST /api/users/login/
* Get User Details: GET /api/users/{id}/
* Update User: PUT/PATCH /api/users/{id}/
* Delete User: DELETE /api/users/{id}/
### Project Management
* List Projects: GET /api/projects/
* Create Project: POST /api/projects/
* Retrieve Project: GET /api/projects/{id}/
* Update Project: PUT/PATCH /api/projects/{id}/
* Delete Project: DELETE /api/projects/{id}/
### Task Management
* List Tasks: GET /api/projects/{project_id}/tasks/
* Create Task: POST /api/projects/{project_id}/tasks/
* Retrieve Task: GET /api/tasks/{id}/
* Update Task: PUT/PATCH /api/tasks/{id}/
* Delete Task: DELETE /api/tasks/{id}/
### Comment Management
* List Comments: GET /api/tasks/{task_id}/comments/
* Create Comment: POST /api/tasks/{task_id}/comments/
* Retrieve Comment: GET /api/comments/{id}/
* Update Comment: PUT/PATCH /api/comments/{id}/
* Delete Comment: DELETE /api/comments/{id}/
## Authentication
This project uses JWT (JSON Web Token) authentication. Obtain a token by logging in (/api/users/login/) and include it in the Authorization header for requests to protected endpoints.

Example header:


Authorization: Bearer <your_access_token>
## Running Tests
To run tests, use the Django test command:


python manage.py test
## Additional Notes
Admin Interface: You can access the Django admin at http://127.0.0.1:8000/admin/ to manage models directly if logged in as a superuser.
Environment Variables: Consider using environment variables to securely store sensitive information such as the SECRET_KEY and database credentials.
