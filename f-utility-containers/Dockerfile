FROM node:14-alpine

WORKDIR /app

ENTRYPOINT [ "npm" ]

# Command: 
# docker build -t mynpm .
# docker run --rm -it -v C:\Users\pepem\Desktop\learning\docker\f-utility-containers:/app mynpm init
# -it (node image requires -it to run)
# docker run --rm -it -v C:\Users\pepem\Desktop\learning\docker\f-utility-containers:/app mynpm install express
# docker run --rm -it -v C:\Users\pepem\Desktop\learning\docker\f-utility-containers:/app mynpm install axios

# Utility containers can be useful for example to setup a project in your local machine even without the languages and tools installed in your computer.
# In this example lets pretend I don't have nodejs installed here and I want to start a node project.

# With the commands above I could uninstall node and npm from my local machine and could still create node projects. It can be useful because with that
# I don't need to install a lot of tools on my machine

# Whenever we add a command after the image name on a docker run the command overwrites the command (CMD) on the dockerfile
# With the ENTRYPOINT I am using in this dockerfile all commands written after the image name will be appended to the entrypoint string.
# With that this dockerfile turns into a npm "engine" even tho I don't have npm on my machine