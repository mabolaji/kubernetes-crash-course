FROM openjdk:8-jdk-alpine

# Copy local code to the container image.
WORKDIR /app
COPY pom.xml ./
COPY src ./src/
# Build a release artifact.
RUN mvn package -DskipTests

VOLUME /tmp
EXPOSE 8080
ADD target/*.jar app.jar
ENTRYPOINT [ "sh", "-c", "java -jar /app.jar" ]
