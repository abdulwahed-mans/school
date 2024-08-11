## My Django and Next.js Project

This project is a web application built using Django for the backend and Next.js for the frontend. It leverages Docker for containerization and Docker Compose for orchestration.

**Table of Contents**

* [Project Structure](#project-structure)
* [Getting Started](#getting-started)
    * [Prerequisites](#prerequisites)
    * [Installation](#installation)
    * [Running the Project](#running-the-project)
* [Technologies Used](#technologies-used)
* [Environment Variables](#environment-variables)
* [Testing](#testing)
* [License](#license)

## Project Structure

```
project_name/
├── backend/  # Django project
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── manage.py
│   └── your_app/  # Replace with your app name
│       ├── settings.py
│       ├── urls.py
│       ├── wsgi.py
│       └── ...
└── frontend/  # Next.js project
    ├── Dockerfile
    ├── package.json
    └── pages/
        ├── index.js
        └── ...
```

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/abdulwahed-mans/school.git
   cd school
   ```

2. **Create a `.env` file for Django (optional):**

   Navigate to the `backend/` directory and create a `.env` file with environment variables specific to your project. Refer to the `Environment Variables` section for details.

3. **Update database settings in `docker-compose.yml` (if using a database):**

   Ensure the database name, user, and password in `docker-compose.yml` match those (if applicable) in the `.env` file or your actual database configuration.

### Running the Project

To run the project using Docker Compose, execute the following command:

```bash
docker-compose up --build
```

This will start the Django backend, Next.js frontend, and any additional services defined in your `docker-compose.yml` file (e.g., database). You can typically access the frontend at `http://localhost:3000` (adjust the port if necessary). The Django admin panel might be accessible at `http://localhost:8000/admin` (default Django admin port).

## Technologies Used

* Django: Backend framework for building the core application.
* Django REST Framework (optional): For building APIs if needed.
* Next.js: React framework for building the frontend.
* (Database name): Database used for storing application data (if applicable).
* Docker: Containerization tool to package and run the application.
* Docker Compose: Tool for defining and running multi-container Docker applications.

## Environment Variables

**(Optional)** The following environment variables can be used in the project:

* `SECRET_KEY`: The secret key for Django (required).
* `DEBUG`: Django debug mode (set to `False` in production).
* Database environment variables (if using a database):
    * `DB_NAME`: The name of the database.
    * `DB_USER`: The database username.
    * `DB_PASSWORD`: The database password.
    * `DB_HOST`: The database host (use `db` when using Docker Compose).
    * `DB_PORT`: The database port (default is 5432).

**Remember to update the `.env` file names and environment variables according to your project's requirements.**

## Testing

**(Optional)** Update the following commands with your specific test runners if applicable:

* To run tests for the Django application (if using Django's test framework):

   ```bash
   docker-compose run django-app python manage.py test
   ```

* To run tests for the Next.js application (if using Jest or another test runner):

   ```bash
   docker-compose run nextjs-app npm run test
   ```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
