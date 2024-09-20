# Use the official Node.js image as the base image
FROM node:20

# Create a non-root user
RUN useradd -m nestuser

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY nest_app/package*.json ./

# Install the dependencies
RUN npm install

# Check permissions of the node_modules/.bin directory
RUN ls -la node_modules/.bin

# Install Nest CLI globally
RUN npm install -g @nestjs/cli

# Copy the rest of your application files
COPY nest_app/ .

# Change ownership of the app files to the non-root user
RUN chown -R nestuser:nestuser /app

# Switch to the non-root user
USER nestuser

# Build the application using shell
RUN sh -c "npm run build"

# Specifies what command to run within the container
CMD ["npm", "run", "start"]

# Indicates that the container will listen on port 3000
EXPOSE 3000
