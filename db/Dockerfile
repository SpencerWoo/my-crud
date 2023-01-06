# docker build . --no-cache -t mysql-mycrud
# docker run -p 3306:3306 -v database:/var/lib/mysql -d mysql-mycrud 

# docker run -p 3306:3306 mysql-mycrud 

# https://hub.docker.com/_/mysql
# https://docs.docker.com/engine/reference/builder/

FROM mysql:5.7

# COPY ./docker.cnf /etc/mysql/conf.d/docker.cnf
COPY ./init.sql /docker-entrypoint-initdb.d/init.sql

ENV MYSQL_DATABASE "my_crud"
ENV MYSQL_ROOT_PASSWORD "mypass"

HEALTHCHECK --interval=20s --timeout=10s --retries=3 \
  CMD curl -f http://localhost:3306 || exit 1

# CMD ["--init-file", "/data/application/init.sql"]
  # mysql-mycrud:
  #   image: mysql:5.7
  #   container_name: mysql-mycrud
  #   volumes:
  #     - ./database:/var/lib/mysql
  #     - ./docker-config/mysql/docker.cnf:/etc/mysql/conf.d/docker.cnf
  #     - ./docker-config/mysql/init.sql:/data/application/init.sql
  #   command: --init-file /data/application/init.sql
  #   restart: always
  #   ports:
  #     - "3306:3306"
  #   environment:
  #     "MYSQL_DATABASE": "my_crud"
  #     "MYSQL_ROOT_PASSWORD": "mypass"
