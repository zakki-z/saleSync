# Use Node.js 20 (required for Next.js 16)
FROM node:20-alpine
# Set the working directory in the container
WORKDIR /app
# Copy package.json and package-lock.json files to the container
COPY code/frontend/package*.json ./
# Install the application dependencies
RUN npm install
# Copy the rest of the application code to the container
COPY code/frontend/ .
# Expose the port that the Next.js application will run on
EXPOSE 3000
# Define the command to run the Next.js application
CMD ["npm", "run", "dev"]