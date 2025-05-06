
# VProfile Project

This project is designed to run a web application with a MySQL database, Memcached, RabbitMQ, and a Tomcat web application using Docker and Docker Compose.

## Project Structure

The project consists of the following services:

- **MySQL**: Database service for storing the application data.
- **Memcached**: In-memory caching service for performance optimization.
- **RabbitMQ**: Message queue service used for communication between different parts of the application.
- **Tomcat Web Application**: A Java web application running on Tomcat.
- **NGINX**: Reverse proxy server for handling HTTP requests.

## Prerequisites

- Docker
- Docker Compose

## Setup Instructions

1. Clone or download the repository.

2. Build and start the Docker containers:

```bash
docker compose up --build -d
```

3. Access the web application in your browser at `http://localhost:8080`.

4. You can also manage RabbitMQ at `http://localhost:15672`.

5. The MySQL service is accessible at `localhost:3306`. Default username: `admin`, password: `admin123`.

## Troubleshooting

- If the MySQL database is not populated correctly, check the logs for errors using:

```bash
docker logs db01
```

- You can manually access the MySQL container to debug and manage the database:

```bash
docker exec -it db01 mysql -u root -p
```

## Notes

- This setup assumes a local development environment.
- Make sure to adjust the database, caching, and message queue configurations in `application.properties` as needed.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

