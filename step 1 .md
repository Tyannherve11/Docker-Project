In this project, we will learn how to solve this problem and practice the technology that revolutionized application distribution
and deployment back in 2013! We are talking of Containers and imply Docker. Even though there are other application containerization
technologies, Docker is the standard and the default choice for shipping your app in a container!


**Side self study: Before starting to work with this project, it is very important to understand what Docker is and what it is used for.
To get a sufficient level of theoretical knowledge it is recommended to take Docker course before you continue with this project.**


Install Docker and prepare for migration to the Cloud
First, we need to install Docker Engine, which is a client-server application that contains:


- A server with a long-running daemon process dockerd.
- APIs that specify interfaces that programs can use to talk to and instruct the Docker daemon.
- A command-line interface (CLI) client docker.


You can learn how to install Docker Engine on your PC [here](https://docs.docker.com/engine/install/)

when instaling docker if you want to pull from hub and have this error:
docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post http://%2Fvar%2Frun%2Fdocker.sock/v1.35/containers/create: dial unix /var/run/docker.sock: connect: permission denied. See 'docker run --help'.

run the command
```
sudo chmod 666 /var/run/docker.sock
```

then pull image
```
docker pull mysql

```
List the images to check that you have downloaded them successfully:

```
docker images
```
Step 2: Deploy the MySQL Container to your Docker Engine
1. Once you have the image, move on to deploying a new MySQL container with:


```
docker run --name <container_name> -e MYSQL_ROOT_PASSWORD=<my-secret-pw> -d mysql/mysql-server:latest
```

or
```
docker run <container ID>
```

- Replace <container_name> with the name of your choice. If you do not provide a name, Docker will generate a random one
- The -d option instructs Docker to run the container as a service in the background
- Replace <my-secret-pw> with your chosen password
- In the command above, we used the latest version tag. This tag may differ according to the image you downloaded
  
  2. Then, check to see if the MySQL container is running: Assuming the container name specified is mysql-server

  
```
docker ps -a
```
