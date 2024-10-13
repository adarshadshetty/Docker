# FROM node:14 as production

# # Set working directory
# WORKDIR /usr/src/client

# # Copy package.json and package-lock.json
# COPY package.json . 
# COPY package-lock.json .

# # Install dependencies
# RUN npm install

# # Install webpack and webpack-cli globally
# RUN npm install -g webpack webpack-cli

# # Copy the rest of the files
# COPY . .

# # Build the application
# RUN npm run build

# # Command to start the app in production mode
# CMD ["sh", "-c", "npm run start:production"]

# Use Node.js version 14 as the base image
FROM node:14 AS production

# Set the working directory for the application
WORKDIR /usr/src/client

# Copy package.json and package-lock.json for dependency installation
COPY package.json . 
COPY package-lock.json .

# Install dependencies, including dev dependencies if needed for the build process
RUN npm install

# Set npm global install directory for PM2 and other global packages
RUN mkdir -p /usr/src/client/.npm-global
RUN npm config set prefix '/usr/src/client/.npm-global'

# Update PATH environment variable for global npm installs
ENV PATH=/usr/src/client/.npm-global/bin:$PATH

# Install PM2 globally
RUN npm install -g pm2 && echo "PM2 installed successfully" || { echo "PM2 installation failed"; exit 1; }

# Install Webpack and Webpack CLI globally if required (for build step)
RUN npm install -g webpack webpack-cli && echo "Webpack installed successfully" || { echo "Webpack installation failed"; exit 1; }

# Copy the rest of the application files into the container
COPY . .

# Build the application (ensure this command is valid in your package.json)
RUN npm run build

# Start the app using PM2 runtime with the correct path to the built application
CMD ["pm2-runtime", "start", "--name", "jira_api", "build/index.js"]
