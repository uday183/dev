# Use the official Node.js image as the base image
FROM node:20.10.0

# Set the working directory
WORKDIR /app

COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy files from your computer into the image
COPY . .

# Install the dependencies
RUN npm run build

# Indicates that the container will listen on port 3000
EXPOSE 3000

# Specifies what command to run within the container
CMD ["npm", "run", "start"]

