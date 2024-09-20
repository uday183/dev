# Use the official Node.js image as the base image
FROM node:20.10.0

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY nest_app/package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of your application files
COPY nest_app/ .

# Debug: Check if necessary files are present
RUN ls -la

# Build the application
RUN npm run build

# Specifies what command to run within the container
CMD ["npm", "run", "start"]

# Indicates that the container will listen on port 3000
EXPOSE 3000
