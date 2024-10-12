FROM node:14 as production

# Set working directory
WORKDIR /usr/src/api

# Copy package.json and package-lock.json
COPY package.json . 
COPY package-lock.json .

# Install dependencies
RUN npm install

# Install webpack and webpack-cli globally
RUN npm install -g webpack webpack-cli

# Copy the rest of the files
COPY . .

# Build the application
RUN npm run build

# Command to start the app in production mode
CMD ["sh", "-c", "npm run start:production"]
