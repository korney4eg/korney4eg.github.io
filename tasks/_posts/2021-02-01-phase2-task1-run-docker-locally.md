---
title: Task 01. Run docker locally.
active: true
published: true
tags: "Phase2"
difficulty: 1
---

Paul, the CTO in your company is very interested in containers technology. You were asked to play with Docker. So in this task you need to setup custom application in container.
<!--more-->

## Task

### 0. Warmup

To learn about docker do following simple tasks:

1. Run locally `nginx` container with exposed port. Make sure that you can access default nginx page on exposed port.
2. Run locally `nginx` container with exposed port and replace default `index.html` file with your own. Make sure that you can access your page on exposed port.
3. Build container `dev-tools` that would be created from `ubuntu` image, and has installed `git`,`make`, `build-essential` packages.
4. Upload previously created image `dev-tools` to dockerhub. Try to pull it from dockerhub.

### 1. Repository

Fork [repository for task05](https://github.com/learningdevops-makvaz-com/phase02_task01) and clone forked repo.

### 2. Build docker image

You need to update `Dockerfile` that has *nginx* with php support, copy file `index.php` to needed folder and make sure nginx and container setup in a way that after starting container you should be able to see rendered php page in your browser by address http://localhost:8080/index.php.
* **Upload your docker image to DockerHub**: Create free account in [DockerHub](https://hub.docker.com/signup). Push your recently built docker image to dockerhub.

### 3. Make your work visible

Create Pull Request with changes on `Dockerfile`.


### Additional tasks if you feel that it was too easy.

1. Instead of copying `index.php` to container find a way to be able to edit this file locally and see your changes after refreshing page.

### Tips:

* Docker allows you manipulating containers. Containers are more lightweight then VM, so it allows to run more applications on the same hardware.

### Recommended soft:

* [Docker](https://www.docker.com/)

### Useful links:

* [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)
* [What is container](https://www.docker.com/resources/what-container)
* [Docker Quickstart](https://docs.docker.com/get-started/)
* [Containers vs Virtual Machines](https://blog.netapp.com/blogs/containers-vs-vms/)

### FAQ

* *N/A*
