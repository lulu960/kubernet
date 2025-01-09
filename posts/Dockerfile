# Use a lightweight Node.js image
FROM node:alpine

# Set the working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package.json ./

RUN npm install

# Copy all the service files
COPY . .

# Expose the service port
EXPOSE 4000

# Default command to run the application
CMD ["node", "index.js"]

