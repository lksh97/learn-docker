# Commands


1. Check the version -
```
docker -v
```

2. Pull docker image (with latest tag/version) - 
```
docker pull [imageName]

example -- docker pull openjdk
```

3. Pull docker image (with specific tag/version) - 
```
docker pull [imageName]:<tagName>

example -- docker pull openjdk:18 
```

4. Checking images on local -
```
docker images
```

5. To search Docker public registry (Docker Hub) for images related to [imageName] -
```
docker search <imageName>
```

6. To start a Docker container using an image [imageName] - There is no output to this command (It starts and close the container when run. See docker ps -a, CREATED & STATUS to verify )
```
docker run <imageName>
```

7. `docker ps` and `docker ps -a` are both commands used with Docker to list containers, but they serve slightly different purposes:

```
docker ps
```
   - This command lists only the currently running containers.
   - It provides information such as Container ID, Image, Command, Created, Status, Ports, and Names.
   - It is helpful for quickly viewing the active containers on your system.

```
docker ps -a
```
   - This command lists all containers, including both running and stopped ones.
   - It provides a more comprehensive view of all containers on your system, regardless of their state.
   - It is useful for troubleshooting, examining past container activity, or managing stopped containers.

   - In summary, `docker ps` is used to view currently active containers, while `docker ps -a` shows all containers, including both running and stopped ones. Depending on your needs, you might use one or the other, or both, to manage Docker containers on your system.

8. The command `docker run --name pythonContainer -d ae29c48b7429` instructs Docker to run a container in the background with the specified image ID `ae29c48b7429` and assign it the name `pythonContainer`. 
```console
docker run --name <containerName> -d <imageId/imageName>

It gives containerID as output
```

```console
docker run --name <containerName> -d <imageName/imageId> -it

**-it** option for interactive mode

example 1-- docker run --name nginxServer -d -p 8080:80 nginx

example 2-- docker run --name httpdServer -d -p 8081:80 httpd

Note : -p option if for ports, check QnA
```

 - Without **-it** flag, Docker starts the container, but if the main process doesn't continue running or if it doesn't have any tasks to perform and exits, Docker considers its job done and stops the container.
- With **-it** flag, Docker waits for input from the terminal. This input keeps Docker thinking that there's something interactive happening, so it doesn't stop the container immediately.
- In summary, using **-it** flag can sometimes prevent the container from stopping immediately because it keeps Docker waiting for interaction. If you want to keep a container running without the need for interaction, you should ensure that there's a long-running process or a service running inside the container.

9. Below command allows you to execute an interactive Python 3 interpreter session within a running Docker container. (get containerName/Id or commandToExecute from **docker ps** or get commandToexecute from docker inspect <containerName/Id> and check value in the command key)
```console
docker exec -it <containerId/containerName> <commandToExecute>

example1 -- docker exec -it 5cc4fc115046 python3
example2 -- docker exec -it javaContainer jshell
```

10. The command docker inspect <containerId> is used to retrieve detailed information about a specific Docker container identified by its Container ID. (get containerId from - **docker ps**)

```console
docker inspect <containerId>
```

11. To stop docker container
```console
docker stop <containerId/containerName/starting3alphaofDockerid ...>

... - means multiple containers at a time
```
This command stops the specified Docker container. You can provide either the Container ID, Container Name, or the starting 3 alphanumeric characters of the Docker ID to uniquely identify the container you want to stop.

It gracefully stops the container(s), allowing running processes inside the container to gracefully shut down.

12. **docker rm** command is used to remove one or more Docker containers from the host system.
```console
docker rm [containerId/containerName/starting3alphaofDockerid ....]

... - means multiple containers at a time
```
It permanently deletes the specified container(s) from the host.
Syntax: docker rm [OPTIONS] CONTAINER [CONTAINER...]

13. **docker rmi command** is used to remove one or more Docker images from the host system. It's used to clean up images that are no longer needed.

```console
docker rmi [imageId/imageName....]

... - means multiple containers at a time
```

You can provide multiple image names or IDs as arguments to remove multiple images at once.

14. `docker restart command` is used to restart a running Docker container. It stops the container if it's currently running and then starts it again.

```console
docker restart <containerId/containerName/starting3alphaofDockerid>
```

When you run docker restart, Docker follows these steps:

- Stops the specified container if it's currently running.
- Starts the container again, using the same configuration and options it had when it was initially started.

This command is useful for restarting containers to apply configuration changes or to troubleshoot issues without having to remove and recreate the container.


More commands -
- Docker kill: Terminates running container processes.
- Docker exec: Executes a command in a running container.
- Docker login: Authenticates a user to a Docker registry.
- Docker commit: Creates a new image from a container's changes.
- Docker push: Uploads images to a registry.
- Docker network: Manages Docker networks.
- Docker history: Shows the history of an image.
- Docker rmi: Removes images.
- Docker ps -a: Lists all containers.
- Docker logs: Retrieves container logs.
- Docker volume: Manages Docker volumes.
- Docker logout: Logs a user out of a Docker registry.