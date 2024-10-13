# Use the official Node.js image as a base
FROM node:16

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json (or yarn.lock) first
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the entire source code into the container
COPY . .

# Install TypeScript globally (if needed) and build the project
RUN npm install -g typescript && npm run build

# Expose the port that your app runs on (e.g., 3000)
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
