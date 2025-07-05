# Working with Container

## Side Hustle Task: Docker Container Operations

### Start a Container and Run a Simple Command:

### 1. Use an official Ubuntu image to start a container. If you don't have the image, you can pull it from docker hub

### 2. Run a simple command within the container, such as displaying the system information.

### 3. Stop the Container and Verify Its Status:

### 4. Stop the running container

### 5. Verify that the container is stopped

### 6. Note the status column to confirm the container's status.

### 7. Restart the Container and Observe Changes:

### 8. Restart the stopped container

### 9. Verify the container's status again to ensure it's running

### 10 Observe any changes or differences in the container's behavior after the restart.

### 11. Remove the Container:

### 12 Stop the running container (if it's still running)

### 13 Remove the container

### 14 Verify that the container is removed

### 15 Confirm that the container is no longer listed.

## Project Implementation

### Running container

![images](screenshot/1.PNG)

### Running container in stay alive mode and verifying container is running

![images](screenshot/2.PNG)

### This will show the system information while keeping the container alive.

![images](screenshot/3.PNG)

### Stopping container and verifying it stopped

![images](screenshot/4.PNG)

### Starting container and confirming container was started

![images](screenshot/5.PNG)

### Stopping running container, removing stopped container and verifying container was does not exist.

![images](screenshot/6.PNG)


## Troubleshooting Container Exits After Run

## What’s Happening Behind the Scenes

### When you run a Docker container, it executes the command you specify (like /bin/bash, uname -a, etc.).

### If that command finishes successfully or there's no ongoing process, the container exits—because its job is done!

## How to Keep Containers Alive

### If you want your container to stay running and usable, run it in interactive mode

Command: `docker run -it --name myubuntu ubuntu /bin/bash`

### `-it`: keeps it interactive and allocates a pseudo-TTY

### `/bin/bash`: gives you a shell session inside the container

### Your container will now stay alive as long as that shell session is open.


## Now, run the container interactively so it stays alive:

### Command: `docker run -dit --name nameyourcontainer nameofimageyouareusingtoruncontainer`

`-d`: detached mode (runs in background)

`-i`: interactive

`-t`: allocates a TTY

`--name`: names the container


## To run a command (like showing system info), use:

### Command: `docker exec ubuntutask uname -a`

### This will show the system information while keeping the container alive.

## Mapping Container

### Mapping a container typically means connecting container ports to host machine ports, so you can access services (like a website or API) from outside the container. In Docker, this is done using the -p flag when running the container.

## Basic Port Mapping Command

`docker run -d -p <host_port>:<container_port> --name <container_name> <image_name>`

## Example:

### If you're running an NGINX container and want to access it on port 8080:

`docker run -d -p 8080:80 --name nginx_container nginx`

- 8080: port on your host (your computer or EC2 instance)

- 80: port inside the container where NGINX listens

- nginx: the Docker image you’re using

## Accessing It:

### Once mapped, you can visit: `http://localhost:8080` (if on your local machine) or `http://<your-public-ip>:8080` (if on a cloud server like AWS EC2)



