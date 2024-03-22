# Use the official Ubuntu image as the base image
# this is base image
FROM ubuntu

# Set the author/maintainer information for the image
MAINTAINER vaibhav

# Update the package index on the Ubuntu image (there's a typo in "apt-update" should be "apt update")
# Use apt-update, If there's an error, the build process will fail
# update command
RUN apt update

# Set the default command to be executed when a container is started from this image
# In this case, it's just echoing a message
# stat up executable command
CMD ["echo", "this is my first ubuntu image"]


# To run -
# # Change directory to the directory containing your Dockerfile
    # cd ubuntu-image/

# # Build the Docker image with the tag "myubuntuimage"
    # docker build -t myubuntuimage .

# # List all Docker images on the system
    # docker images

# # Run a container from the "myubuntuimage" image with the name "myUbuntuContainer"
    # docker run --name myUbuntuContainer myubuntuimage