A Netflix clone built with Django, Python, Javascript, and sqlite.

## Features
- User authentication (sign up, login, logout)
- Homepage with movie list and featured movie
- Movie details page
- Genre-based filtering
- Search functionality
- Personal movie list management

## Technologies Used
- **Backend:** Django, Python
- **Database:** PostgreSQL
- **Frontend:** HTML, CSS, JavaScript
- **File Storage:** Local storage for images and videos

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/netflix-clone.git
   cd netflix-clone
   ```

2. **Set up the environment and install dependencies:**
   ```bash
   python -m venv env
   source env/bin/activate
   pip install -r requirements.txt
   ```

3. **Run migrations and start the server:**
   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

4. **Open the app in your browser:**
   Visit `http://127.0.0.1:8000/`.

---------------------------------------------------------------------
## API Documentation

#### User Authentication

- **Sign Up**
  - **URL:** `/signup.html`
  - **Method:** `POST`
  - **Payload:**
    ```json
    {
      "email": "user@example.com",
      "username": "username",
      "password": "password123",
      "password2": "password123"
    }
    ```
  - **Responses:** 
    - **200 OK** for successful sign-up.
    - **400 Bad Request** for validation errors (e.g., email or username taken, passwords do not match).

- **Login**
  - **URL:** `/login`
  - **Method:** `POST`
  - **Payload:**
    ```json
    {
      "username": "username",
      "password": "password123"
    }
    ```
  - **Responses:** 
    - **200 OK** for successful login.
    - **401 Unauthorized** for invalid credentials.

- **Logout**
  - **URL:** `/logout`
  - **Method:** `GET`
  - **Responses:** 
    - **200 OK** for successful logout.

#### Movie Management

- **Search**
  - **URL:** `/search`
  - **Method:** `POST`
  - **Payload:**
    ```json
    {
      "search_term": "movie title"
    }
    ```
  - **Responses:**
    - **200 OK** with search results.
    - **400 Bad Request** for missing `search_term`.

#### User List Management

- **Add to List**
  - **URL:** `/add-to-list`
  - **Method:** `POST`
  - **Payload:**
    ```json
    {
      "movie_id": "uuid-of-movie"
    }
    ```
  - **Responses:**
    - **200 OK** with status message (e.g., `{"status": "success", "message": "Added ✓"}`).
    - **400 Bad Request** for invalid request.

- **Remove from List**
  - **URL:** `/remove-from-list`
  - **Method:** `POST`
  - **Payload:**
    ```json
    {
      "movie_id": "uuid-of-movie"
    }
    ```
  - **Responses:**
    - **200 OK** with status message (e.g., `{"status": "success", "message": "Removed ✓"}`).
    - **400 Bad Request** for invalid request.

