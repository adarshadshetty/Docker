# FROM node:14 AS production

# # Set working directory
# WORKDIR /usr/src/api

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

FROM node:14 AS production

# Set working directory
WORKDIR /usr/src/api

# Copy package.json and package-lock.json
COPY package.json . 
COPY package-lock.json .

# Install dependencies
RUN npm install

# Set npm global install directory
RUN mkdir -p /usr/src/api/.npm-global
RUN npm config set prefix '/usr/src/api/.npm-global'

# Update PATH environment variable for global npm installs
ENV PATH=/usr/src/api/.npm-global/bin:$PATH

# Install PM2 globally and log output
RUN npm install -g pm2 && echo "PM2 installed successfully" || { echo "PM2 installation failed"; exit 1; }

# Check if PM2 is installed and log the installation directory
RUN ls /usr/src/api/.npm-global/bin || echo "Global npm directory not found."

# Install webpack and webpack-cli globally (if required)
RUN npm install -g webpack webpack-cli || { echo "Webpack installation failed"; exit 1; }

# Copy the rest of the application files
COPY . .

# Build the application (if needed)
RUN npm run build

# Start the app using PM2 runtime
CMD ["pm2-runtime", "start", "--name", "jira_api", "node", "--", "-r", "./tsconfig-paths.js", "build/index.js"]
