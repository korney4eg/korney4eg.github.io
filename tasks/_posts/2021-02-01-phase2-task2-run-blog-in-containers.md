---
title: Task 02. Run Wordpress in docker.
active: true
published: true
tags: "Phase2"
heroes: []
difficulty: 3
---

"Video Games Magazine" become so popular that it was decided to hire programmer that would create plugins for wordpress that would customize your site. One day appeared girl named Mei. Mei asked you to setup her wordpress in docker on her laptop, so that she can develop locally. After you proposed to use Vagrant she answered that Vagrant and VMs is The Prehistoric Period and she want's to have something modern.

<!--more-->

## Task

### 1. Repository

* Fork [repository for task02](https://github.com/learningdevops-makvaz-com/phase02_task02) and clone forked repo.

### 2. Build docker image

* **Build wordpress image 1**:You need to update `Dockerfile` that has *nginx* with php support, to setup wordpress with predefined theme and [thank-after-post plugin **v0.8.0**](https://github.com/korney4eg/thank-after-post-plugin/releases/download/v0.8.0/thank-after-post.zip). Then build docker image with unique tag.
* **Build wordpress image 2**:You need to update `Dockerfile` that has *nginx* with php support, to setup wordpress with predefined theme and [thank-after-post plugin **v0.9.0**](https://github.com/korney4eg/thank-after-post-plugin/releases/download/v0.9.0/thank-after-post.zip). Then build docker image  with unique tag.

### 3. Upload images to public container regisry using GitHub actions

* **Create GitHub workflow**: Workflow should build image on every update of `master` branch, tag this image with unique tag and push it to one of the public repositories of your choice.

### 4. Run local Wordpress setup in containers

* **Describe docker containers**: Update `docker-compose.yml` file so that two containers started: `database` that uses `mysql` docker image, and `wordpress` that connects to `database`.
* **Work localy**: Make sure that after starting `docker-compose` you able to see, login, create posts on wordpress by accessing it through [http://localhost](http://localhost), or [https://localhost](https://localhost) if you want to configure it with HTTPS.
* **Work with different images**: On previous step you create two docker images with different plugin version. To check if it works perfectly try to run wordpress with one image, create post and make sure that you see thank after your post text when publishing. Then update image name with tag that contains plugin version `v0.9.0` and publish new post. It should have newer version of plugin
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
