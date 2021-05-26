---
title: Task 03. Multicontainer setup. Beginning of CI.
published: true
active: true
tags: "Phase2"
difficulty: 3
---

When you come to the workplace, Paul your manager and CTO of the company asked you to help with Mei's work. She took a vacation for one week. Now it seems that the plugin was written by Mei working properly. She even wrote some tests. Paul mentioned that you need to add an additional check of the plugin version to the test. He also added that Mei sent you an e-mail with more info.
<!--more-->
## Email from Mei

>Hi,
>I really sorry, that you need to do my work. Paul asked me to give you more information about testing.
>
>First of all, let me tell you the purpose of those tests. Currently, I'm working on the "thanks-after-post" plugin and I would like to know that it's working properly. So every time I finish the development of the plugin, I can run tests and check that all text is displayed as needed. For example, after every new post, the plugin should add "Thank you for reading!" and show the plugin version. Actually it's part of [Contineous Integration](https://www.atlassian.com/continuous-delivery/continuous-integration). Would be great to implement the CI process at least in our company. What do you think?
>
>I've implemented a test that checks if "Thank you for reading!" is displayed after every post. Right now you should add a check for the plugin version. The code of the test is pretty straightforward, so I think you would be able to easily understand it and correct it.
>
>One more time sorry, for making you touching my work. On the other hand, you can understand more what I'm doing. Maybe someday you teach me more administration tasks. Anyway, I gonna bring something yummy from vacations.
>
>Best regards,
>Mei.


## Task

### 1. Repository

* Fork [repository for task03](https://github.com/learningdevops-makvaz-com/phase02_task03) and clone forked repo.

### 2. Build docker image

* **Build wordpress image 1**:You need to update `Dockerfile` that has *nginx* with php support, to set up wordpress with predefined theme and [thank-after-post plugin **v0.10.0**](https://github.com/korney4eg/thank-after-post-plugin/releases/download/v0.10.0/thank-after-post.zip). Then build docker image with unique tag.

### 3. Run local WordPress multiapp setup in containers.

* **Describe docker containers**: Update `docker-compose.yml` file so that two containers started: `database` that uses `mysql` docker image, and `wordpress` that connects to `database`.
* **Configure through environment variables**: Make sure that all configuration is set through environment variables.
* **Work localy**: Make sure that after starting `docker-compose` you are able to see, login, create posts on wordpress by accessing it through [http://localhost](http://localhost), or [https://localhost](https://localhost) if you want to configure it with HTTPS. There should be `2` replicas of wordpress with the plugin version `v0.10.0`. Also there should be loadbalancer service(any application you want) that proxyes traffic to one of two replicas.

### 4. Run tests.

* Fork [repository with tests](https://github.com/learningdevops-makvaz-com/tests) and clone forked repo.
* Setup your testing environment. Check `README.md` for instructions.
* Run tests in interactive way. There test will open Chrome browser window and run test there. Don't forget to set all needed environment variables.
* Update `test.py` so that it checks plugin version.
* Update `test.py` sot that it runs tests in noninteractive way. Browser would not be opened.
* Build docker image with tests. This image you will use in one of the next tasks.

### 5. Make your work visible.

* Create Pull Request with all changes for task 3.
* Create Pull Request with all changes for tests.


### Additional tasks if you feel that it was too easy.

1. *N/A*

### Tips:

* Docker compose is next level of manipulating docker containers. It allows to get its logs, see running containers and get many more information.
* Keep all needed environment variables in one file. This file can be share with different services.


### Recommended soft:

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/)
* [Selenium](https://www.selenium.dev/)

### Useful links:

* [Dockerfile reference](https://docs.docker.com/engine/reference/builder/)
* [Docker Quickstart](https://docs.docker.com/get-started/)
* [Overview of Docker Compose](https://docs.docker.com/compose/)
* [Selenium with Python](https://selenium-python.readthedocs.io/getting-started.html)

### FAQ

* *N/A*
