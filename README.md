# Guide for first 10 checklist items

### Creating a Dockerfile for a Simple Static Website

```
# Use an official NGINX runtime as a parent image
FROM nginx:latest

# Set the working directory to /usr/share/nginx/html
WORKDIR /usr/share/nginx/html

# Copy the contents of the current directory to /usr/share/nginx/html
COPY . .

# Expose port 80
EXPOSE 80

# Start NGINX and keep it running in the foreground
CMD ["nginx", "-g", "daemon off;"]
```

### Building the Docker Image
docker build -t my-nginx-image .

### list docker images
`docker images`

### Running the Docker Container
`docker run -d --name my-container -p 8080:80 my-nginx-image`

### list docker containers
`docker ps -a`

### Check the website in the browser
`http://localhost:8080`

### Stop the Docker Container
`docker stop my-container`

### Remove the Docker Container
`docker rm my-container`

### Remove the Docker Image
`docker rmi my-nginx-image`

### Remove all Docker Images
`docker rmi $(docker images -aq)`

### DockerHub
`create a repository on DockerHub`

### build the image with the tag for DockerHub
`docker build -t <dockerhub-username>/<image-name>:tag-name .`

### push the image to DockerHub
`docker push <dockerhub-username>/<image-name>:tag-name`

### pull the image from DockerHub
`docker pull <dockerhub-username>/<image-name>:tag-name`

### run the image from DockerHub
`docker run -d --name my-container -p 8080:80 <dockerhub-username>/<image-name>:tag-name`

### Executing Commands in a Running Docker Container
`docker exec -it my-container bash`

### run any command in the container
```
ls -l
cat <file-name>
```

### exit from the shell
`exit`

### Stop the Docker Container
`docker stop my-container`

### Remove the Docker Container
`docker rm my-container`

### Remove the Docker Image
`docker rmi <dockerhub-username>/<image-name>:tag-name`
