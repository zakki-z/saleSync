# Stage 1: Build
FROM eclipse-temurin:17-jdk AS build
WORKDIR /app
# Copy Maven wrapper and pom.xml
COPY code/backend/mvnw .
COPY code/backend/.mvn .mvn
COPY code/backend/pom.xml .
# Download dependencies
RUN ./mvnw dependency:go-offline
# Copy source code
COPY code/backend/src ./src
# Build the application
RUN ./mvnw clean package -DskipTests

# Stage 2: Runtime
FROM eclipse-temurin:17-jre AS runtime
WORKDIR /app
# Copy the built JAR from build stage
COPY --from=build /app/target/*.jar /app/salesync-backend.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app/salesync-backend.jar"]