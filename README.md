# docker-scripts
A Sample hello world docker scripts for learning purpose

## Docker Installation

  please visit the docker site for Installation

### Issues faced while running the basic docker hello-world base image

    docker login

"docker login" command is must - (asks for authentication), otherwise you can't pull the basic images for execution from docker's registry

### Docker Baseimage - alpine

    docker run alpine:latest "echo" "Hello, World"

### Now compile the "HelloWorld.java" file

  javac HelloWorld.javac

### Execute the class file to check whether the Hello world message printed in the console

  java HelloWorld

### Create a Dockerfile & copy-paste the below content in Dockerfile

FROM alpine:latest
ADD HelloWorld.class HelloWorld.class
RUN apk --update add openjdk8-jre
ENTRYPOINT ["java", "-Djava.security.egd=file:dev/./urandom", "HelloWorld"]

# Build an image from the created Dockerfile

    docker build --tag "docker-hello-world:latest" .

# After the image is re-built, now run the docker image to check the latest message

    docker run docker-hello-world:latest
