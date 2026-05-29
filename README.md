# Flask TODO App – REST API Enhancement (IT6 Final Drill)

## Project Overview

This project enhances an existing Flask TODO web application by adding a **REST API layer** that implements full CRUD (Create, Read, Update, Delete) functionality.

The original application provides a basic task management system with a web interface. This enhancement introduces an API that allows tasks to be managed programmatically using Swagger documentation.
# Flask TODO App – REST API Enhancement

##  Overview

This project is an enhancement of an existing Flask TODO web application.  
The original system was a simple web-based task manager that uses HTML templates to add, view, update, and delete tasks.

The improvement made in this project is the addition of a **REST API with full CRUD functionality**, along with Swagger documentation and unit testing.


## Changes Made to the Original Project

### 1. Added REST API (CRUD Functionality)

A new API layer was created using Flask Blueprints under `/api`.

New endpoints added:

- `GET /api/tasks` – Retrieve all tasks
- `GET /api/tasks/<id>` – Retrieve a single task
- `POST /api/tasks` – Create a new task
- `PUT /api/tasks/<id>` – Update an existing task
- `DELETE /api/tasks/<id>` – Delete a task

These endpoints allow the application to be used programmatically without relying on the web interface.


### 2. Integrated Swagger Documentation

Swagger (Flasgger) was added to document and test all API endpoints.

- Accessible at: `/apidocs`
- Allows interactive testing of all CRUD operations
- Shows request and response formats clearly


### 3. Improved Project Structure

The application was reorganized using Flask Blueprints:

- `routes.py` → Handles original UI (login and tasks page)
- `api.py` → Handles REST API logic
- `models.py` → Shared database model (Task)

This separation improves code readability and maintainability.


### 4. Shared Database for UI and API

Both the original web interface and the new API use the same database.

This ensures that:
- Changes made in Swagger reflect in the UI
- Changes made in the UI reflect in the API


### 5. Added Unit Testing

Unit tests were implemented using `pytest`.

Tests cover:
- Creating tasks
- Reading tasks
- Updating tasks
- Deleting tasks
- Error handling (invalid IDs, missing data)


##  Summary of Improvements

| Feature | Original App | Enhanced App |
|--------|-------------|-------------|
| Task Management | UI only | UI + REST API |
| Data Access | Web interface | API + Web |
| Documentation | None | Swagger UI |
| Testing | None | Unit tests added |
| Architecture | Basic Flask | Blueprint-based structure |

---

##  Conclusion

The project successfully enhances the original Flask TODO application by adding a REST API layer, Swagger documentation, and unit testing. This makes the system more flexible, scalable, and suitable for integration with other applications such as mobile apps or external services.

## Technologies Used

* Python
* Flask
* Flask-SQLAlchemy
* Flasgger (Swagger UI)
* SQLite
* Pytest / Unittest



## Project Structure


Flask-TODO-APP/
│
├── app/
│   ├── __init__.py        # App factory + Swagger setup
│   ├── models.py          # Task database model
│   ├── api.py             # REST API (CRUD endpoints)
│   ├── routes.py          # Original UI routes (HTML pages)
│   └── templates/
│       ├── login.html
│       └── tasks.html
│
├── tests/
│   └── test_api.py       # Unit tests for API
│
├── run.py                # Entry point
├── requirements.txt
└── README.md
```

---

##  Features Implemented

###  Original Application (UI)

* Login page (`/login`)
* Task list page (`/tasks`)
* Add task (form submission)
* Toggle task completion
* Delete task


###  REST API Features

All API endpoints are documented using Swagger.

####  Base URL

```
http://127.0.0.1:5000/api
```

---

###  API Endpoints

#### 1. Get all tasks

```
GET /api/tasks
```

#### 2. Get single task

```
GET /api/tasks/<id>
```

#### 3. Create task

```
POST /api/tasks
```

Request body:

```json
{
  "title": "My Task"
}
```

---

#### 4. Update task

```
PUT /api/tasks/<id>
```

Request body:

```json
{
  "title": "Updated Task",
  "complete": true
}
```

---

#### 5. Delete task

```
DELETE /api/tasks/<id>
```

---

## 📊 Swagger Documentation

Swagger UI is available at:

```
http://127.0.0.1:5000/apidocs
```

It allows:

* Testing all API endpoints
* Viewing request/response formats
* Interactive API documentation

---

## Testing

Unit tests were created using `pytest`.

### Run tests:

```bash
pytest
```

### Test Coverage:

* Create task (POST)
* Get all tasks (GET)
* Get single task (GET by ID)
* Update task (PUT)
* Delete task (DELETE)
* Negative cases (404 handling)

---

## 🔁 How to Run the Project

### 1. Clone Repository

```bash
git clone <your-forked-repo-url>
cd Flask-TODO-APP
```

### 2. Create Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate   # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run Application

```bash
python run.py
```

---

##  Access the App

### UI Pages

* Login Page: [http://127.0.0.1:5000/login](http://127.0.0.1:5000/login)
* Tasks Page: [http://127.0.0.1:5000/tasks](http://127.0.0.1:5000/tasks)

### API Documentation

* Swagger UI: [http://127.0.0.1:5000/apidocs](http://127.0.0.1:5000/apidocs)

---

##  Key Improvements Made

* Added full REST API (CRUD functionality)
* Integrated Swagger for API documentation
* Connected UI and API to a shared database
* Added unit testing for all API endpoints
* Improved modular structure using Blueprints

---

##  Notes

* This project is an enhancement of an existing Flask TODO application.
* Only backend/API improvements were implemented as required.
* No frontend redesign was required for grading.

---

##  Author

Tan, Joram Jr. G. – IT6 Final Drill
REST API Enhancement of Flask TODO Application
