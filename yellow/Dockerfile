# Use the specified base image
FROM node:17.0-alpine3.14

# Set the working directory inside the container
WORKDIR /app

# Update apk and install a specific version of npm
RUN apk add --no-cache npm=7.17.0-r0

# Copy package.json and package-lock.json to the /app directory
COPY package*.json /app/

# Install dependencies
RUN npm install

# Copy the app.js file to the /app directory
COPY app.js /app/

# Create the /app/views directory and copy index.pug and favicon.ico
RUN mkdir -p /app/views
COPY index.pug /app/views/
COPY favicon.ico /app/views/

# Copy the rest of the application code to the /app directory
COPY . /app/

# Expose port 80
EXPOSE 80

# Define the command to run the application
CMD ["node", "./app.js"]
