# Use the official Node.js image as the base image
FROM node:20

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY nest_app/package*.json ./

# Install the dependencies
RUN npm install


# Install Nest CLI globally
RUN npm install -g @nestjs/cli

# Copy the rest of your application files
COPY nest_app/ .

# Build the application using shell
RUN sh -c "npm run build"

# Specifies what command to run within the container
CMD ["npm", "run", "start"]

# Indicates that the container will listen on port 3000
EXPOSE 3000
