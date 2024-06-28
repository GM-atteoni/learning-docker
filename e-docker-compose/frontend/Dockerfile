FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . . 

EXPOSE 3000

CMD ["npm", "start"]

# For the node app
# image: docker build -t goal-react .
# container: docker run --rm -p 3000:3000 --network network-goal --name goal-web goal-react