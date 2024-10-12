# Base image for this node project java script 'AS' means the Production environment like Tag
FROM node:14 AS Production 

# This is a Production base Environment
ENV NODE_ENV=production

# Change the currently working dir to another dir , '/usr/src/api' whole application buld inside the docker container inside this dir
WORKDIR /usr/src/api

# Copies to the this dir /usr/src/api
COPY package.json . 

# Copies to the this dir /usr/src/api
COPY package.lock.json .

# Install all the dependencies
RUN npm install 

# Everything copies to the local dir to docker container
COPY . .

# Build the application into zip file
RUN npm run build

# Run this command inside the container
CMD [ "sh", "-c", "npm run start:production" ]
