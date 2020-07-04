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
docker build -t docker_image_name:tag_version dockerfile_path
```

### Create docker container from docker image 
```bash
docker run -itd --name container_name -p port_number docker_image_name:tag_version
``` 

### List docker containers to show inactive containers
```bash
docker container ls -a
```

### Stop a docker container 
```bash
docker container stop container_name
```

### Delete a docker container 
```bash
docker container rm container_name
```

### Delete a docker image
```bash
docker image rm docker_image_name:tag_version
```