### Pull docker images from Docker hub 
```bash
docker pull ubuntu:latest
docker pull r-base
docker pull python:3.8 
```

### List docker images 
```bash
docker images
```

### Build docker image from dockerfile
```bash
docker build -t docker_image_name:tag_version -f Dockerfile dockerfile_path
```

### Create docker container from docker image 
```bash
docker run -itd --name container_name -p port_number docker_image_name:tag_version
``` 

### List docker containers to show inactive containers
```bash
docker container ls -a
```

### Follow container logs
```bash
docker container logs --follow container_name
```

### Stop a docker container 
```bash
docker container stop container_name
```

### Delete a docker container forcefully 
```bash
docker container rm -f container_name
```

### Delete a docker image
```bash
docker image rm docker_image_name:tag_version
```

### Prune docker images
```bash
docker image prune
```

### Prune docker system
```bash
docker system prune
```

### Save a docker image to tar file 
```bash
## method 1
docker save --output image_name.tar image_name:tag
## method 2 
docker save image_name:tag > gzip > image_name_tag.tar.gz
```
### Load docker image from file 
```bash
## method 1
docker load < image_name_tag.tar.gz
## method 2
docker load --input image_name.tar
```
### Commit changes to container and save it as an image 
```bash
docker commit [CONTAINER_ID] [new_image_name]
```
