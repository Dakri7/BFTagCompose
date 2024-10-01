# Use an official OpenJDK image as the base image
FROM debian
ENV JAVA_HOME=/opt/java/openjdk
COPY --from=eclipse-temurin:21 $JAVA_HOME $JAVA_HOME
ENV PATH="${JAVA_HOME}/bin:${PATH}"

# Set the working directory inside the container
WORKDIR /app

# Install git
RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

# Clone the repository
RUN git clone https://github.com/Dakri7/BFTagServer.git /app

# Set the working directory to the project folder inside the container
WORKDIR /app

# Build the Spring Boot project (requires Maven)
RUN apt-get update && apt-get install -y maven && mvn clean install

# Expose the port that the Spring Boot server will run on
EXPOSE 8080

# Run the Spring Boot application
CMD ["java", "-jar", "target/BFTagServer-0.0.1-SNAPSHOT.jar"]