FROM mysql:8.0.33

ENV MYSQL_ROOT_PASSWORD=admin123
ENV MYSQL_DATABASE=accounts

COPY 01-init.sql /docker-entrypoint-initdb.d/
COPY db_backup.sql /docker-entrypoint-initdb.d/

