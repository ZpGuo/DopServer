FROM alpine:3.8

LABEL MAINTAINER="goozp <gzp@goozp.com>"
LABEL APP="mariadb"

ENV TIMEZONE Asia/Shanghai
ENV MYSQL_ROOT_PASSWORD root
ENV MYSQL_DATABASE dopserver
ENV MYSQL_USER dopserver
ENV MYSQL_PASSWORD dopserver
ENV MYSQL_USER_MONITORING monitoring
ENV MYSQL_PASSWORD_MONITORING monitoring

# Installing packages MariaDB
RUN apk add --no-cache mysql
RUN addgroup mysql mysql

# Work path
WORKDIR /scripts

# Copy of the MySQL startup script
COPY scripts/start.sh start.sh

# Creating the persistent volume
VOLUME [ "/var/lib/mysql" ]

EXPOSE 3306

ENTRYPOINT [ "./start.sh" ]