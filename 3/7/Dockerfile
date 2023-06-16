# Start from the alpine image that is smaller but no fancy tools
FROM node:16-alpine

EXPOSE 5000

ENV REACT_APP_BACKEND_URL=http://localhost:8080

# Use /usr/src/app as our workdir. The following instructions will be executed in this location.
 WORKDIR /usr/src/app

# Copy the hello.sh file from this location to /usr/src/app/ creating /usr/src/app/hello.sh
 COPY . .

# Alternatively, if we skipped chmod earlier, we can add execution permissions during the build.
#RUN chmod +x ./mvnw

RUN npm install && npm run build && npm install -g serve && adduser -D frontenduser
 
USER frontenduser

# When running docker run the command will be java -jar ./target/docker-example-1.1.3.jar
CMD ["serve", "-s", "-l", "5000", "build"]