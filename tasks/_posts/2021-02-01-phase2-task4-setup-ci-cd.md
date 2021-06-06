---
title: Task 04. Setup CI/CD for WordPress with containers using Jenkins.
published: true
tags: 
  - "Phase2"
  - jenkins
  - docker
active: true
---

<!--more-->

## Task

### 1. Repository

* Fork [repository for task04](https://github.com/learningdevops-makvaz-com/phase02_task04) and clone forked repo.
* Fork [repository with thank-after-post WordPress plugin](https://github.com/korney4eg/thank-after-post-plugin) and clone forked repo.

### 2. Start up local jenkins from repository

* **Set proper values for `.env` file**: In `.env` file change value of **SEED_JOBS_URL** variable to url of your forked repo. This repo would be used to store your pipeline configuration changes.
* **Start jenkins server**: On your cloned repository from task 4 start docker-compose.

### 3. Create manual job to add tags to wordpress plugin.

* **Create your first Jenkins job**: 
You should create job that will take two string parameters:
  * `plugin_url` - it will be used to point to repo for your plugin URL
  * `new_tag` - new version of plugin that you can set manualy

Job should do following:
  1. Clone repository of your `thank-after-post` forked repo
  2. Get the latest tag
  3. Increment minor version of the tag. For examle, you had tag `v0.9.0` then next version should be `v0.10.0`. For more info check [this site](https://semver.org/)
  4. Uag repo with incremented version and push to remote
  5. Trigger `deploy_dev` pipeline and set `plugin_version` as your updated version, `git_url` - repo of `thank-after-post` plugin.

### 4. Update pipeline `deploy_dev`.

#### 4.1. Update `build_wp_image` stage.

* **Build docker wordpress docker image with newly created plugin**: build wordpress image with provided version of plugin.

#### 4.2. Run docker-compose with new wordpress image.

Configure this stage to do following things:
  1. On the repo from task 02 update `docker-compose.yaml` file, so that exposed port on wordpress and image version of the wordpress would be readed from environment variable. For more help check out [this page](https://docs.docker.com/compose/environment-variables/).
  2. Clone repo from  task 02.
  3. export variable for wordpress tag from `plugin_version`
  4. Export variable for exposed port by wordpress on dev enivronment. For example: `81`
  5. Run `docker-compose` in detached mode, so that you are able to login to started wordpress blog.

#### 4.3. Run tests.

* Run container with tests that you created for task 03 to test that new plugin was successfully deployed on wordpress.

#### 4.4. Clean dev environment.

* **Run `docker-compose down -v` for dev environment**


### 5. Create `deploy_prod` pipeline.

* **Copy `deploy_dev` job configuration**: copy file `job_configs/deploy_dev.groovy` to `deploy_prod`. And make proper changes in this file.

* **Copy `deploy_dev` job**: copy file `jobs/deploy_dev.groovy` to `deploy_prod`. And make proper changes in this file.

* **Input parameters should be same as for `deploy_dev` pipeline**

* **Key difference in `deploy_prod` from `deploy_dev`**:
  1. exposed port should be `80`, not `81`.

#### 4.5. Add trigger to start `deploy_prod` from `deploy_dev`


### 6. Make your work visible

* Create Pull Request with all changes for task 4.
* Create Pull Request with all changes for task 3.


### Additional tasks if you feel that it was too easy.

1. *N/A*

### Tips:

* Take your time to understand how jenkins work.
* If you check out job configuration `scriptPath` it reads file. This file is also called `Jenkinsfile`.
* After jenkins creation there would be only one `z_seed_job` in dashboard. To load all your pipelines you should run this job.
* To check your changes to any stage you need to commit and push your changes to the repo.
* If you make changes to job configuration (for example create new `deploy_prod` pipeline) you need to commit and push your changes, then to run `z_seed_job` manualy.
* If you make changes to job, you only need to commit and push changes to repo and just manualy trigger `deploy_dev` job.


### Recommended soft:

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/)
* [Selenium](https://www.selenium.dev/)
* [Jenkins](https://www.jenkins.io/)

### Useful links:

* [Job configuration manual](https://jenkinsci.github.io/job-dsl-plugin/)
* [Jenkins configuration examples](https://github.com/jenkinsci/pipeline-examples)
* [Docker Quickstart](https://docs.docker.com/get-started/)
* [Overview of Docker Compose](https://docs.docker.com/compose/)
* [Selenium with Python](https://selenium-python.readthedocs.io/getting-started.html)

### FAQ

* *N/A*
