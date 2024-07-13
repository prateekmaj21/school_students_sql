# school_students_sql
The objective of this project is to develop a complete application that performs CRUD (Create, Read, Update, Delete) operations on a MySQL database using Python. 

# Prerequisites

## MySQL Database Setup

1. Ensure you have MySQL Server installed and running.
2. Create a database named `school` and a table named `students` with appropriate columns (`id`, `name`, `age`, `grade`). Refer to the instructions for setting up the database.

## Python Environment

1. Make sure you have Python installed on your system. You can download Python from [python.org](https://www.python.org) if not already installed.

# Project Files

1. **database.py**: Implement MySQL connection and CRUD operations.
2. **main.py**: Implement FastAPI application with CRUD endpoints.
3. **requirements.txt**: List the Python dependencies (fastapi, uvicorn, mysql-connector-python).

---

## requirements.txt

```text
fastapi==0.70.0
uvicorn==0.15.0
mysql-connector-python==8.0.28
```

# How to Use:

Create a new file named requirements.txt in your project directory.
Copy the above dependencies into `requirements.txt`.

Install these dependencies using pip:

```text
pip install -r requirements.txt
```
By including these dependencies in your requirements.txt file, you ensure that anyone setting up your FastAPI project can easily install the necessary packages with a single command.

# Install uvicorn Globally

UVICORN is an ASGI (Asynchronous Server Gateway Interface) web server implementation tailored for Python.
```text
pip install uvicorn
```
To run it: 
```text
uvicorn main:app --reload

python -m uvicorn main:app --reload
```

Once uvicorn starts your FastAPI application successfully, you should see output indicating that the server is running, usually on `http://127.0.0.1:8000` by default.

### Terminate the Server:

To stop the FastAPI application, press `Ctrl + C` in the terminal or command prompt where the server is running.

### MySQL Server

```text
import mysql.connector
from mysql.connector import Error

def create_connection():
    connection = None
    try:
        connection = mysql.connector.connect(
            host="localhost",
            user="root",
            password="1234",
            database="school"
        )
        print("Connection to MySQL DB successful")
    except Error as e:
        print(f"The error '{e}' occurred")
    return connection
```
**host:** The hostname or IP address where your MySQL server is running. Typically, if it's on your local machine, you use "localhost".

**user:** The username to authenticate with the MySQL server.

**password:** The password corresponding to the username for authentication.

**database:** The name of the database you want to connect to.

### Create Database and Table:

```text
CREATE DATABASE school;
USE school;
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    grade VARCHAR(10) NOT NULL
);
```




