## Docker images and container
An image is an executable package that includes everything needed to run an application--the code, a runtime, libraries, environment variables, and configuration files.

A container is a runtime instance of an image--what the image becomes in memory when executed (that is, an image with the state, or a user process).

A Docker image can be compared to a git repository. Just like a git repository, it can be hosted on GitHub, Bitbucket, GitLab, or even a private git repo hosting service, but we could host our Docker image on Docker repository hosting service like Docker Hub.

Docker Hub is a service provided by Docker for hosting, finding, and sharing Docker Repositories. A docker repository can be public or private. Docker HUb is an exaample of a prublic repository. A third-party repository hosting services also exists. The Docker Hub and other third party repository hosting services are called registries. A registry has many repositories, while a repository has many different versions of the same image.

### Search the Docker Hub for Images
We could also look up and find images on Docker Hub by either using the search bar on the website or using the below command:
```
docker search <image_name>
```

### Pull an Image or a Repository from a Registry
To download a particular image, or set of images, use `docker pull`. If no tag is provided, Docker Engine uses the :latest tag as a default.

```
docker pull <image_name>:<tag_name>
```

### Uploading an image to Docker Hub
1.Sign up for docker hub

2.Sign in to Docker Hub and click on ‘Create Repository’ on the Docker Hub welcome page

3.Fill in the repository name. Also, describe your repo like "My First Repository". Finally, click on the create button

### Uploading an image to Docker Hub
1. Log into the Docker public registry from your local machine terminal using Docker CLI

```
docker login
```

2. Tag the image
The image can be official or unofficial. If it is an unofficial image, it should be named as follows ` <username>/<image_name>:<tag_name>`. The command used is;

```
docker tag <image_name>:latest <username>/<image_name>:latest
```

3. Publish the image
Use the `docker push` command to upload yor tagged image into the repository

```
docker push <username>/<image_name>:latest
```

4. Test out your image
One can test the image you uploaded by running;

```
docker pull <username>/<image_name>:latest
$ docker run -it <username>/<image_name>:latest
```

5. Saving the image
One can use the `docker save` command to save the image you have pulled
