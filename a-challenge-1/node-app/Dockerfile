FROM node

WORKDIR /app

# I can use . here because the WORKDIR changed the context to /app so after the WORKDIR: . = /app
COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "server.js"]