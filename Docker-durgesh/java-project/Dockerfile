# Use the official OpenJDK 11 image as the base image
FROM openjdk:11

# Set the working directory inside the container
WORKDIR /usr/src/myapp

# Copy the current directory contents into the container at /usr/src/myapp
COPY . /usr/src/myapp/

# Compile and run the Java file Test.java inside the container
RUN java Test.java

# Set the default command to run when the container starts
CMD ["java", "Test"]
