# docker build . --no-cache -t backend
# docker run -p 9001:9001 backend

FROM node:15

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install

COPY . .
# COPY start_application.sh /

# ENTRYPOINT ["/start_application.sh"]
HEALTHCHECK --interval=20s --timeout=10s --retries=3 \
  CMD curl -f http://localhost:9001 || exit 1

CMD ["npm", "run", "dev"]

  # node-mycrud:
  #   container_name: node-mycrud
  #   image: node:15
  #   ports:
  #    - "9001:9001"
  #   volumes:
  #    - ./backend:/application
  #    - ./docker-config/node/start_application.sh:/start_application.sh
  #   restart: always
  #   entrypoint: /start_application.sh
  #   healthcheck:
  #    test: ["CMD-SHELL", "curl -f http://localhost:9001"]
  #    interval: 20s
  #    timeout: 10s
  #    retries: 3
