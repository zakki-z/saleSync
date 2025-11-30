# Use an official Node.js runtime as a parent image
FROM node:18
# Set the working directory in the container
WORKDIR /app
# Copy package.json and package-lock.json files to the container
COPY package*.json ./
# Install the application dependencies
RUN npm install
# Copy the rest of the application code to the container
COPY . .
# Expose the port that the Next.js application will run on
EXPOSE 3000
# Define the command to run the Next.js application
CMD ["npm", "run", "dev"]