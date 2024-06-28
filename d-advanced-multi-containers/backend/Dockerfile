FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . . 

EXPOSE 80

ENV MONGO_DB_USERNAME=defaultUsername
ENV MONGO_DB_PASSWORD=defaultPassword

CMD ["node", "app.js"]


# For mongodb
# docker run -d --rm --name mongodb -e MONGO_INITDB_ROOT_USERNAME=mongo -e MONGO_INITDB_ROOT_PASSWORD=mongo --network network-goal -v data:/data/db mongo

# For the node app
# image: docker build -t goal-node .
# network: docker network create network-goal
# container: docker run -d --rm -p 80:80 --network network-goal -e MONGO_DB_USERNAME=mongo -e MONGO_DB_PASSWORD=mongo --name goal-app -v logs:/app/logs -v app/node_modules goal-node




