# MySQL Docker Setup

This repository provides a simple setup for running MySQL in a Docker container. You can use either Docker directly or Docker Compose to manage your MySQL instance.

## Prerequisites

- **Docker** installed on your machine [Docker](https://www.docker.com).
- **Docker Compose** installed (if using the Docker Compose method)

## Getting Started

### Using Docker

To start a MySQL container using Docker, run the following command:

```bash
docker run --name mysql-container \
  -e MYSQL_ROOT_PASSWORD=rootpassword \
  -e MYSQL_DATABASE=mydatabase \
  -e MYSQL_USER=myuser \
  -e MYSQL_PASSWORD=mypassword \
  -p 3306:3306 \
  -d mysql:latest
```

## Command Explanation:

<p>
--name mysql-container: Names the container mysql-container.<br>
-e MYSQL_ROOT_PASSWORD=rootpassword: Sets the MySQL root password.<br>
-e MYSQL_DATABASE=mydatabase: Creates a database named mydatabase.<br>
-e MYSQL_USER=myuser: Creates a new user myuser.<br>
-e MYSQL_PASSWORD=mypassword: Sets the password for myuser.<br>
-p 3306:3306: Maps port 3306 of the container to port 3306 on your host.<br>
-d mysql:latest: Uses the latest MySQL image from Docker Hub and runs the container in detached mode.
</p>

### Using Docker Compose

## To start a MySQL container using Docker Compose, follow these steps:

1. Create a docker-compose.yml file with the following content:

    ```yaml
    version: '3.1'
    services:
      mysql:
        image: mysql:latest
        container_name: mysql-container
        environment:
          MYSQL_ROOT_PASSWORD: rootpassword
          MYSQL_DATABASE: mydatabase
          MYSQL_USER: myuser
          MYSQL_PASSWORD: mypassword
        ports:
          - 3306:3306
    ```

2. Run the following command to start the MySQL container:

```bash
docker-compose up -d
```

## Accessing the MySQL Instance

Once the container is running, you can connect to the MySQL instance using your preferred MySQL client with the following connection details:

Host: localhost
Port: 3306
Username: myuser
Password: mypassword
Database: mydatabase

## Stopping and Removing the Container

To stop the MySQL container:

```bash
docker stop mysql-container
```

To remove the container:

```bash
docker rm mysql-container
```

If using Docker Compose:

```bash
docker-compose down
```

Troubleshooting

Ensure Docker is running and properly configured on your system.
Check the container logs with docker logs mysql-container for any issues.

License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
