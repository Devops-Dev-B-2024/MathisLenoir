FROM mysql

ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=tp2
ADD mysql_backup.sql /docker-entrypoint-initdb.d

EXPOSE 3306