Step 1: Create a Node.js Application
const http = require('http');

const hostname = '0.0.0.0';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});


Step 2: Create a Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose the port the app runs on
EXPOSE 3000

# Define the command to run the app when the container starts
CMD [ "node", "app.js" ]


Step 3: Build the Docker Image
docker build -t my-node-app .

Step 4: Run the Docker Container
docker run -p 3000:3000 my-node-app

Step 5: Test the Application
open http://localhost:3000








