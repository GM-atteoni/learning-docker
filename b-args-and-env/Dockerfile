FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

# This is just a varibale (build time argument) in the dockerfile to facilitate fixes and changes.
ARG DEFAULT_PORT=80

# This statement will provide a PORT variable into the node process.env object. Be aware that for this if we want to inject a port from outside
# the container we need to "docker run" with a new command (--env or -e), this command injects a env variable mapped to the ENV dockerfile
ENV PORT $DEFAULT_PORT

EXPOSE $PORT

# This statement could replace the anonymous volume (-v /app/node_modules). Named volumes and bindmounts cannot.
# VOLUME [ "/app/node_modules" ]

CMD [ "npm", "start" ]

# Command: docker run -d --rm -p 3000:8000 --env PORT=8000 --name feedback-app -v feedback:/app/feedback 
# -v C:\Users\pepem\Desktop\learning\docker\b-dealing-with-bindmounts\:/app -v /app/node_modules -v /app/temp feedback-node:volumes2