# Use an official Node.js runtime as the base image with the desired Node.js version (18.16.1 in your case)
FROM node:18.16.1

# Install Angular CLI globally with the desired version (16.1.8 in your case)
RUN npm install -g @angular/cli@16.1.8

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Build the Angular app for production
RUN ng build --configuration=production

# Expose a port (e.g., 80) to run the app
EXPOSE 80

# Start the Angular app when the container starts
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "80"]
