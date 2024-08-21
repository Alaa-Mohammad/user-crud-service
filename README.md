# User CRUD Service

This project is a simple Django REST API that provides CRUD (Create, Read, Update, Delete) operations for a `User` model. The API is implemented using the Django REST framework and allows basic operations on a user entity with attributes: `username`, `password`, and `active`.

## Features

- **Create**: Add a new user.
- **Read**: Retrieve a list of users or a specific user.
- **Update**: Modify an existing user's details.
- **Delete**: Remove a user from the database.

## Tech Stack

- **Django** - High-level Python web framework.
- **Django REST Framework** - Powerful and flexible toolkit for building Web APIs.

## Installation

1. **Clone the repository:**

    ```bash
    git clone <repository-url>
    cd usercrud
    ```

2. **Create a virtual environment and activate it:**

    ```bash
    python3 -m venv env
    source env/bin/activate  # On Windows use `env\Scripts\activate`
    ```

3. **Install the required packages:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Apply migrations:**

    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

5. **Run the development server:**

    ```bash
    python manage.py runserver
    ```

## API Endpoints

The following endpoints are available:

- **GET /api/users/**  
  Retrieve a list of all users.

- **POST /api/users/**  
  Create a new user.
  - **Request Body**:
    ```json
    {
      "username": "your_username",
      "password": "your_password",
      "active": true
    }
    ```

- **GET /api/users/{id}/**  
  Retrieve details of a specific user.
  - **Response**:
    ```json
    {
      "id": 1,
      "username": "your_username",
      "password": "your_password",
      "active": true
    }
    ```

- **PUT /api/users/{id}/**  
  Update details of a specific user.
  - **Request Body**:
    ```json
    {
      "username": "updated_username",
      "password": "updated_password",
      "active": false
    }
    ```

- **DELETE /api/users/{id}/**  
  Delete a specific user.

## Project Structure

- `usercrud/` - Main Django project directory.
- `api/` - Application directory containing the `User` model, serializers, views, and URLs.
- `requirements.txt` - Contains the list of dependencies.

## Testing the API

You can test the API using tools like [Postman](https://www.postman.com/) or `curl`. Here are a few example commands using `curl`:

- **Create a new user:**
    ```bash
    curl -X POST http://127.0.0.1:8000/api/users/ -d '{"username":"user1", "password":"pass123", "active":true}' -H "Content-Type: application/json"
    ```

- **Get all users:**
    ```bash
    curl http://127.0.0.1:8000/api/users/
    ```

- **Get a specific user:**
    ```bash
    curl http://127.0.0.1:8000/api/users/1/
    ```

- **Update a user:**
    ```bash
    curl -X PUT http://127.0.0.1:8000/api/users/1/ -d '{"username":"updated_user", "password":"newpass", "active":false}' -H "Content-Type: application/json"
    ```

- **Delete a user:**
    ```bash
    curl -X DELETE http://127.0.0.1:8000/api/users/1/
    ```



## Contact

For any inquiries, feel free to reach out via [alaamohammad027@gmail.com] or open an issue in the repository.

