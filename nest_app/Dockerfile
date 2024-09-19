# Use the official Node.js image as the base image
FROM node:20.10.0

# Set the working directory
WORKDIR usr/src/app

# Copy application dependency manifests to the container image.
# A wildcard is used to ensure copying both package.json AND package-lock.json (when available).
# Copying this first prevents re-running npm install on every code change.
COPY --chown=node:node package*.json ./

RUN npm install

# Copy files from your computer into the image
COPY nest_app/ .

# Install the dependencies
RUN npm install


# Specifies what command to run within the container
CMD ["npm", "run", "start"]

# Indicates that the container will listen on port 3000
EXPOSE 3000