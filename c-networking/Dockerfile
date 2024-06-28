FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["node", "app.js"]

# For communication with any World Wide Web api should work with no configuration!
# For local communication:  localhost = host.docker.internal

# mongoose.connect(
#   'mongodb://localhost:27017/swfavorites',
#   ...

#  AFTER THE CHANGE

# mongoose.connect(
#   'mongodb://host.docker.internal:27017/swfavorites',
#   ...

# 1) For container -> container communication we need to inspect (docker container inspect [name]) the running target container and get its IPAddress to use it on the URL. 

# 2) For container -> container communication we can create shared networks and pass it into the docker run command (--network [name]) and passing it with the 
# same name for multiple containers create a communication layer between them:

# docker network create favorites-net
# docker run -d --name mongodb --network favorites-net mongo (Database)
# docker run --name favorites-app --rm -d -p 5000:3000 --network favorites-net favorites-node (App)

# with that I can change the host of any request to the container's name and Docker will manage to send it to the correct place. 