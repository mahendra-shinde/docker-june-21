FROM mysql:5.7

ENV MYSQL_DATABASE=sample MYSQL_USER=mahendra MYSQL_PASSWORD=pass12345 MYSQL_ROOT_PASSWORD=pass@12345

## This should work with MSSQL and PostgreSQL databases
COPY *.sql /docker-entrypoint-initdb.d/