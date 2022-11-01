# To understand Docker Architecture and Container Life Cycle

lets start with the basic docker commands

## Docker Commands

0. Before running the below commands make sure you are having root access 
```bash
sudo su
```
1. To check the docker version
```bash
docker --version
```
2. To check the docker info
```bash 
docker info
```
3. To check the docker images
```bash
docker images
```
4. To pull images from the docker repository
```bash
docker pull <image_name>
```
eg:
```bash
docker pull ubuntu
```
5. To create a container from an image
```bash
docker run -it ubuntu
```

6. To list the running containers
```bash
docker ps
```

7.  To show all the running and exited containers
```bash
docker ps -a
```
8. To access the running container
```bash
docker exec -it <container_id> bash
```
>you can get the container id by running the command `docker ps` by checking the first column of running containers

9. To stop the running container
```bash
docker stop <container_id>
```
or
```bash
docker kill <container_id>
```
>This command kills the container by stopping its execution immediately. The
difference between ‘docker kill’ and ‘docker stop’ is that ‘docker stop’ gives the
container time to shutdown gracefully, in situations when it is taking too much time
for getting the container to stop, one can opt to kill it

10. Following command lists all the locally stored docker images
```bash
docker images
```
11. To delete a stopped container we can remove the container using the following command
```bash
docker rm <container_id>
```
12.  To delete an image from local storage
```bash
docker rmi <image_id>
```
or
```bash
docker rmi <image_name>
```
>you can get the image id by running the command `docker images` by checking the first column of images and image name by checking the second column of images.

### Let's create a container from an mysql image .

```bash
docker run --name {conatinername} -e MYSQL_USER=user -e MYSQL_PASSWORD=root -e MYSQL_DATABASE=apple -e MYSQL_ROOT_PASSWORD=root -d mysql
```
```bash
docker exec -it {containerid recieved from above command} bash
```
>The docker exec command allows you to run commands in a running container. The -i flag tells Docker to keep STDIN open to your container, and the -t flag allocates a pseudo-TTY. This basically allows you to have an interactive shell session with your container.

### check the apple database
```bash
mysql -u root -p
```
```bash
show databases;
```












