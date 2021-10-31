# Cloud Course Archive and Notes

## TP1 : Discovery of Docker

### Build an image
```
docker build . -f Dockerfile -t image_tag
```
### Launch container
```
docker run -it --rm --name name-container image_tag
```
### Link two containers
```
docker build . -f Dockerfile1 -t image_tag1
docker build . -f Dockerfile2 -t image_tag2

docker run -it --rm --name container_name1 image_tag1

docker run -it --rm --name container_name2 --link container_name1:host_name image_tag2
```