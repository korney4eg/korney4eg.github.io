---
title: Task 01. Run docker locally.
active: true
published: true
tags: "Phase2"
---

Paul, the CTO in your company is very interested in containers technology. You were asked to play with Docker. So in this task you need to setup custom application in container.
<!--more-->

## Task

* **Repository**: Fork [repository for task05](https://github.com/learningdevops-makvaz-com/phase02_task01) and clone forked repo.
* **Build docker image** : You need to update `Dockerfile` that will install *nginx* with php support, copy file `index.php` to needed folder and make sure nginx and container setup in a way that after starting container you should be able to see rendered php page in your browser by address http://localhost:8080/index.php.
* **Redirect to HTTPS**: Add nginx configuration that will redirect all requests from http://localhost:8080 to https://localhost:8443. Make sure that port 8443 is also configured on nginx and in Docker.
* **Upload your docker image to DockerHub**: Create free account in [DockerHub](https://hub.docker.com/signup). Push your recently built docker image to dockerhub.

### Additional tasks if you feel that it was too easy.
1. Instead of copying `index.php` to container find a way to be able to edit this file locally and see your changes after refreshing page.

### Tips:

* Docker allows you manipulating containers. Containers are more lightweight then VM, so it allows to run more applications on the same hardware.

### Recommended soft:

* [Docker](https://www.docker.com/)

### Usefull links:

* [Vagrant - multiple VMs](https://www.vagrantup.com/docs/multi-machine)
* [Docker Quickstart](https://docs.docker.com/get-started/)

### FAQ

* *N/A*
