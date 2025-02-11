# Docker Basics  

Docker is a software for deploying and running containerized applications.  
It solves problems using **containers**, which are isolated groups of processes.  

Docker is similar to a virtual machine, but VMs are slower and have their own OS, while Docker shares the host OS.  

---

## Basic Docker Commands  

### 1. Verify Docker Installation  
To check if Docker is installed correctly, run:  
```sh
docker run hello-world
```
If successful, you will see the message:  
> "Hello from Docker! This message shows that your installation appears to be working correctly."

---

### 2. Pull an Image  
To pull the **BusyBox** image from the Docker registry and install it on your system:  
```sh
docker pull busybox
```

---

### 3. View Downloaded Images  
To list all images available on your system:  
```sh
docker images
```

---

## 4. Run a Container  
To create and run a container using the **BusyBox** image:  
```sh
docker run busybox
```
**Note:**  
If nothing happens in the command prompt, that means Docker created the container and ran the command. Since no command was specified, the container was created and exited immediately.  

---

## 5. Delete Containers  

### Delete a Specific Container  
```sh
docker rm <ContainerID>
```
On deletion, you should see the container ID echoed back.  

### 6. Delete All Exited Containers  
```sh
docker rm $(docker ps -a -q -f status=exited)
```
- `-q` flag returns only numeric container IDs.  
- `-f` flag filters output based on the specified condition (in this case, `status=exited`).  

### 7. Prune Unused Containers  
```sh
docker container prune
```
This command removes all stopped containers.  

### 8. Delete an Image  
```sh
docker rmi busybox
```
This removes the **BusyBox** image from the system.  

### 9. Check space taken by docker
```sh
docker system df
```
This will show how much space is taken by docker in your system

### 10. Removes build cache
```sh
docker builder prune
```




### More Commands Coming Soon 🚀  
