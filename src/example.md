# MySQL Docker Setup

## Option 1: Docker Command

```bash
docker run --name mysql-container \
  -e MYSQL_ROOT_PASSWORD=rootpassword \
  -e MYSQL_DATABASE=mydatabase \
  -e MYSQL_USER=myuser \
  -e MYSQL_PASSWORD=mypassword \
  -p 3306:3306 \
  -d mysql:latest
```

## Option 2: Docker Compose

```bash
docker-compose up -d
```

Note: Ensure you have a docker-compose.yml file configured for the second option.
