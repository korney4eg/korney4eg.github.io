---
title: Task 03. Automating start of containers.
active: true
published: false
tags: "Phase2"
heroes: []
difficulty: 3
---


Here would be first lesson
"Video Games Magazine" become so popular that it was decided to hire programmer that would create plugins for wordpress that would customize your site. One day appeared girl named Mei. Mei asked you to setup her wordpress in docker on her laptop, so that she can develop locally. After you proposed to use Vagrant she answered that Vagrant and VMs is The Prehistoric Period and she want's to have something modern.

<!--more-->

## Task

### 1. Repository

* Fork [repository for task04](https://github.com/learningdevops-makvaz-com/phase02_task04) and clone forked repo.

### 2. Run WordPress in container in VM

* **Provision Wordpress** : Setup Wordpress using Ansible and Vagrant, but this time there would be two VMs:
  1. `database`, where MySQL is running
  2. `wordpress`, where Wordpress is running inside containers in a way that should automatically restarted on VM reboot and it should be easy to stop and start wordpress same as other linux services.
* **Open ports**: Make sure that port 3306 on `database` is open for application in `wordpress` vm. 

### 3. Run tests inside wordpress VM

* **Configure through environment variables**: Make sure that all configuration is set through environment variables.

### 5. Make your work visible

* Create Pull Request with changes on `Dockerfile` and `docker-compose.yml` files.


### Additional tasks if you feel that it was too easy.

1. *N/A*

### Tips:

* Docker compose is next level of manipulating docker containers. It allows to get it's logs, see running containers and get many more information.

### Recommended soft:

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/)

### Useful links:

* [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)
* [Docker Quickstart](https://docs.docker.com/get-started/)
* [Overview of Docker Compose](https://docs.docker.com/compose/)

### FAQ

* *N/A*
