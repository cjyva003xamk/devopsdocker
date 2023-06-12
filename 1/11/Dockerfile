# Start from the alpine image that is smaller but no fancy tools
FROM openjdk:8

EXPOSE 8080

# Use /usr/src/app as our workdir. The following instructions will be executed in this location.
 WORKDIR /usr/src/app

# Copy the hello.sh file from this location to /usr/src/app/ creating /usr/src/app/hello.sh
 COPY . .

# Alternatively, if we skipped chmod earlier, we can add execution permissions during the build.
#RUN chmod +x ./mvnw

# clean up the file
RUN sed -i 's/\r$//' ./mvnw

RUN ./mvnw package

# When running docker run the command will be java -jar ./target/docker-example-1.1.3.jar
CMD ["java", "-jar","./target/docker-example-1.1.3.jar"]