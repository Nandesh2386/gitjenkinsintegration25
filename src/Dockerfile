# Use the OpenJDK image from Docker Hub
FROM openjdk:11-jdk-slim

# Copy application JAR to the container
COPY target/YourApp.jar /app.jar

# Run the Java application
ENTRYPOINT ["java", "-jar", "/app.jar"]
