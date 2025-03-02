# Recipe App API

This is a Django-based API for managing recipes, tags, and ingredients. The project uses Docker and Docker Compose for containerization and deployment.

## Features

- User authentication and authorization
- Recipe management (CRUD operations)
- Tag management (CRUD operations)
- Ingredient management (CRUD operations)
- Image upload for recipes
- Filtering recipes by tags and ingredients
- API documentation with drf-spectacular

## Requirements

- Docker
- Docker Compose

## Setup

### Environment Variables

Create a `.env` file in the root directory of the project and add the following environment variables:

```env
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASS=your_db_password
DJANGO_SECRET_KEY=your_secret_key
DJANGO_ALLOWED_HOSTS=your_allowed_hosts
```

### Build and Run
To build and run the project, use the following commands:

```
docker-compose build

docker-compose up
```

### Deployment
To deploy the project, use the docker-compose-deploy.yml file:

```
docker-compose -f docker-compose-deploy.yml build
docker-compose -f docker-compose-deploy.yml up
```

### Project Structure
- app: Contains the Django application code
- proxy: Contains the Nginx configuration and run script
- docker-compose.yml: Docker Compose configuration for development
- docker-compose-deploy.yml: Docker Compose configuration for deployment
- Dockerfile: Dockerfile for building the Django application image
- Dockerfile: Dockerfile for building the Nginx proxy image
- run.sh: Script to start Nginx with environment variable substitution

### API Documentation
The API documentation is generated using drf-spectacular and can be accessed at /api/api/docs/ after starting the application.

### Running Tests
To run the tests and check linting, use the following command:

```
docker-compose run --rm app sh -c "python manage.py test && flake8"
```