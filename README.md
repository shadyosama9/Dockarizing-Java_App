# Dockarizing Java App

This repository contains the Dockerfiles and Docker Compose configuration to dockerize a Java application with MySQL database, Nginx, and other services.

## Project Structure

- **Docker-files/db**: Contains the Dockerfile for the MySQL database.
- **Docker-files/app**: Contains the Dockerfile for the Java application (Tomcat).
- **Docker-files/web**: Contains the Dockerfile for Nginx.

## Docker Compose Setup

The `docker-compose.yml` file defines the services for the project:

- **vprodb**: MySQL database container.
- **vprocache01**: Memcached container.
- **vpromq01**: RabbitMQ container.
- **vproapp**: Tomcat container for the Java application.
- **vproweb**: Nginx container.

## Instructions

1. Clone the repository:

   ```sh
   git clone https://github.com/your-username/Dockarizing-Java_App.git
- Build the Docker images and start the containers:
    ```sh
    docker-compose up --build
    ```
- Access the application at [http://localhost:8080](http://localhost:8080).

## Configuration

- MySQL: Default root password is `admin` and the database name is `accounts`.
- Nginx: Configuration file is located at `Docker-files/web/nginvproapp.conf`.
- Java App: The WAR file is deployed to the root context (`/`) of Tomcat.

## Author

- Shady Osama



