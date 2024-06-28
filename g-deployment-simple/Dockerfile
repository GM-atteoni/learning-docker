FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

CMD ["node", "app.js"]

# Bindmounts and productions environment: Bindmounts are an useful way to have a smooth development process were the container code is in our local machine,
# we can use our local project folder as a bindmount so we don't need to run many builds and runs to see the changes.
# In production the idea is that the container is standalone and it does not depends on nothing. The image should be the source of truth.
# Therefone, when in production we use COPY (COPY . .) instead of the bindmount, so we copy a source code snapshot into the image.


# Connecting to EC2 instance:
# Create and launch EC2 instance, VPC and security group (last 2 are default)
# Configure security group to expose all required ports to WWW
# Connect to instance (SSH), install docker and run container

# To connect to my EC2 instance, I am using OpenSSH on windows just by using the ssh -i key.pem user@ip. I've faced a problem about the key or smt like that
# and to fix it I just changed the key file security to have only me as the owner (removing system and administrator).

# After accessing the EC2 instance I ran "sudo yum update -y" to ensure all essential packages are updated and running latest versions
# then "sudo amazon-linux-extras install docker" this makes easier to install docker on the remote machine (idk if it is always needed)
# "sudo service docker start" to start docker there. After that we are able to run docker commands (i.e. docker run)

# To run our image on the EC2 instance we will follow this steps:
# Build image locally "docker build -t pepematt/node-example-1 ."
# Push image to docker hub (local machine) "docker push pepematt/node-example-1"
# Pull image from docker hub (remote machine)
# Run image (remote machine)

# By default the EC2 instance is basically disconnected from everything in WWW (except you with SSH)
# To change that we need to access the security group of the EC2 instance. By adding a new inbound rule to accept HTTP connections on port 80
# from anywhere. With that people can access my running node server inside the EC2 by HTTP