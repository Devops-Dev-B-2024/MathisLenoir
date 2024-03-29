FROM mysql

ENV MYSQL_ROOT_PASSWORD=root
ADD mysql_backup.sql /docker-entrypoint-initdb.d

EXPOSE 3306