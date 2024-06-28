FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# VOLUME ["/app/node_modules"] this can be a substitute for -v /app/node_modules

CMD ["node", "server.js"]

# Command: docker run -d --rm -p 3000:80 --name feedback-app -v feedback:/app/feedback (this is a named volume) 
# -v C:\Users\pepem\Desktop\learning\docker\b-dealing-with-bindmounts\:/app (this is a bind mount
# where the path is the relative path to the local folder) -v /app/node_modules (this is a anonymous folder) 
# -v /app/temp (this is another anonymous folder) feedback-node:volumes2 (image)

# 1-) To work with bind mounts you just need to use a new command in docker run (similar to volumes). (-v path-to-local-folder:/app) 
# path-to-local-folder = path to local folder on your machine that will be used as a bind mount and you have access to it and can 
# manage things inside (on volumes, you cannot manage things inside) /app = name of the folder in the container (this folder will always be mounted
# with whatever is inside your choosen local folder)

# 2-) Now this will not working as intended, the container is being replaced with the files in the choosen local folder and with that the
# node_modules folder is being deleted after created. To fix that we can create a new volume (not bind mount) with the node_modules folder
# (because volumes will not be replaced with the stuff in the choosen local folder) so -v /app/node_module)

# The key difference between volumes and bind mounts (since both are created with -v) is that for volumes you just need to specify 
# which container folder you want DOCKER to "volumerize" and for bind mounts you need to firstly insert the local folder and then the
# container folder. With that docker wont manage the volume so it is a bind mount

# We can notice here that because we are creating 2 new volumes called feedback and node_modules inside our container
# and the container is binded to our local folder (in the host machine) those volumes (or folders) will be created on the 
# local folder too. (Didn't find a solution for this but it shouldn't be a problem)

# BIND MOUNTS SHOULDN'T BE USED IN PRODUCTION!!