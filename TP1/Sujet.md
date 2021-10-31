# Subject
Manipulation on containers
1. Install Docker on its machine
2. create and run a container writing a string on
a port
3. create and run a container doing processing on
a string received on a port and displaying the result on
another port
4. chain these two containers using —link

## Deploy the containers

### Build the images

```
docker build . -f Dockerfile_Client -t client
docker build . -f Dockerfile_Server -t server
```
### Launch ```server-container```
``` 
docker run -it --rm --name server-container server
``` 
With ``` -it ``` the container becomes interactive, can be kill with ``` Ctrl+C ```.
With ``` --rm ``` the container will be deleted as soon as it is stopped.

### Launch ```client-container```
```
docker run -it --rm --name client-container --link server-container:server-host client
```
``` --link ``` makes the container ```server-container``` visible. It will be avaible under the host name ```server-host```.