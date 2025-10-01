# Use the official Node.js 20 image as the base image
FROM node:20

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Remove node_modules and package-lock.json, then install dependencies
RUN rm -rf node_modules package-lock.json && yarn install --network-timeout 1000000

# Copy the rest of the application code
COPY . .

# Build the application for production
RUN yarn run build

# Expose the port the app runs on
EXPOSE 5188

# Start the application in preview mode on port 5188
CMD ["yarn", "run", "preview", "--", "--port", "5188"]

