# docker build . --no-cache -t backend
# docker run -p 9001:9001 backend

FROM node:15

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install

COPY . .

HEALTHCHECK --interval=20s --timeout=10s --retries=3 \
  CMD curl -f http://localhost:9001 || exit 1

CMD ["npm", "run", "dev"]