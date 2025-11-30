# Use an official OpenJDK runtime as a parent image
FROM openjdk:21-jdk-alpine
# Set the working directory in the container
WORKDIR /app
# Copy the Spring Boot application JAR file into the container
COPY target/salesync-backend.jar /app/salesync-backend.jar
# Expose the port that the Spring Boot application will run on
EXPOSE 8080
# Define the command to run the Spring Boot application
ENTRYPOINT ["java","-jar","/app/salesync-backend.jar"]