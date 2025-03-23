#  Project: User Management
This project is a web application for managing users. It provides a RESTful API for user registration, login, logout, and retrieving a list of users. The project uses Flask, Flask-Login, Flask-Restful, and other libraries to ensure security and ease of working with user data.

### Key Features:

- User Registration: Users can register by providing their data (username, password, gender, date of birth, etc.).

- User Login: Users can log in using their credentials.

- User Logout: Users can log out of the system.

- CSRF Token Retrieval: For protection against CSRF attacks.

- User List Retrieval: Administrators can view a list of all registered users.


### Technologies and Libraries Used:


Flask (==2.0.2): A lightweight web framework for Python that provides simplicity and flexibility for web application development.

Flask-SQLAlchemy (==2.5.1): A Flask extension that integrates ORM (Object Relational Mapping) into Python applications, simplifying database interactions.

Flask-Login (==0.6.3): A library for managing user sessions, providing login and logout functionality.

Flask-WTF (==1.0.0): A Flask extension that integrates form handling libraries, including CSRF protection.

Flask-Bcrypt (==1.0.1): A library for password hashing, ensuring the security of user credentials.

marshmallow (==3.23.2): A library for object serialization and deserialization, enabling easy data exchange between the application and the client.

PostgreSQL: A relational database management system (RDBMS) used in the project for reliable storage and management of user data.


## Installing a project:

1. Clone the Repository:
```
git clone https://github.com/kostoyanskaya/draught.git

or

git clone git@github.com:kostoyanskaya/draught.git
```

2. Navigate to the Project Directory:

```
cd draught
```

3. Create a Virtual Environment:

```
python -m venv venv
```

4. Activate the Virtual Environment:

```
source venv/Scripts/activate
```

5. Upgrade pip:

```
python -m pip install --upgrade pip
```

6. Install Dependencies:

```
pip install -r requirements.txt
```

7. Create a .env File:
"It is not necessary to do this; SQLite is connected by default."

8. Create a .env file in the project root directory and fill it as follows:
"It is not necessary to do this; SQLite is connected by default."
```
FLASK_APP=task_app
FLASK_DEBUG=1
DATABASE_URI=postgresql://username:password@localhost:5432/database_name
SECRET_KEY=YOUR_SECRET_KEY
```

9. Run the Following Commands:
```
python migrate.py init
python migrate.py migrate "Text"
python migrate.py upgrade

```

10. Start the Application:

```
python run.py
```

## Example Requests:

```
Method: GET

Retrieve CSRF Token:
URL: http://127.0.0.1:5000/api/get_csrf
```

## Include the CSRF Token in Requests:
For every subsequent request (e.g., registration, login, logout), include the CSRF token in the request headers. The token should be passed in the X-CSRF-TOKEN header.


```
Method: GET

Retrieve User List:
URL: http://127.0.0.1:5000/api/get_users
```



```
Method: POST

http://127.0.0.1:5000/api/register_user
```
body:
```
{
    "username": "testuser",
    "password": "testpassword",
    "full_name": "Test User",
    "gender": "male",
    "birth_date": "1990-01-01"
}
```
```
Method: POST

http://127.0.0.1:5000/api/login_user
```
body:
```
{
    "username": "testuser",
    "password": "testpassword"
}
```



```
Method: POST

User Logout:
URL: http://127.0.0.1:5000/api/logout_user
```



## author
#### [_Виктория_](https://github.com/kostoyanskaya/)