FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

CMD ["node", "server.js"]

# Command: docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback feedback-node:volumes

# To work with volumes you just need to use a new command in docker run. (-v feedback:/app/feedback) feedback = name of the volume
# /app/feedback = name of the folder in the container