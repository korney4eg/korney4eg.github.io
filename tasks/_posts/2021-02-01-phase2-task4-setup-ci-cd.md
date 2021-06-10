---
title: Task 04. Setup CI/CD for WordPress with containers using Jenkins.
published: true
difficulty: 3
tags: 
  - "Phase2"
  - jenkins
  - docker
active: true
---
Mei - the main developer in Gamer Magazine who returned from vacation jumped to active work on the Wordpress plugin. Together you started to figure out how the development and deployment process could be improved. You found out that the best bet would be to implement Continuous Integration/ Continuous Delivery with help of Jenkins.
<!--more-->
In this task, you will need to implement the whole process of [Contineous Integration](https://www.martinfowler.com/articles/continuousIntegration.html)/[Contineous Delivery](https://www.martinfowler.com/delivery.html) using one of the most popular tools - Jenkins.

## Task

### 1. Repository

* Fork [repository for task04](https://github.com/learningdevops-makvaz-com/phase02_task04) and clone forked repo.
* Fork [repository with thank-after-post WordPress plugin](https://github.com/korney4eg/thank-after-post-plugin) and clone forked repo.

### 2. Startup local Jenkins from the repository

* **Set proper values for `.env` file**: In `.env` file change value of **SEED_JOBS_URL** variable to URL of your forked repo. This repo would be used to store your pipeline configuration changes.
* **Start Jenkins server**: On your cloned repository from task 4 start docker-compose.

### 3. Create a manual job to add tags to the wordpress plugin.

* **Create your first Jenkins job**: 
You should create a job that will take two string parameters:
  * `plugin_url` - it will be used to point to the repo for your plugin URL
  * `new_tag` - a new version of the plugin that you can set manually

A job should do the following:
  1. Clone repository of your `thank-after-post` forked repo
  2. Get the latest tag
  3. Increment minor version of the tag. For example, you had tag `v0.9.0` then the next version should be `v0.10.0`. For more info check [this site](https://semver.org/)
  4. Uag repo with incremented version and push to remote
  5. Trigger `deploy_dev` pipeline and set `plugin_version` as your updated version, `git_url` - repo of `thank-after-post` plugin.

### 4. Update pipeline `deploy_dev`.

#### 4.1. Update `build_wp_image` stage.

* **Build docker wordpress docker image with newly created plugin**: build wordpress image with a provided version of the plugin.

#### 4.2. Run docker-compose with new wordpress image.

Configure this stage to do the following things:
  1. On the repo from task 02 update the` docker-compose.yaml` file, so that the exposed port on wordpress and image version of the wordpress would be read from an environment variable. For more help check out [this page](https://docs.docker.com/compose/environment-variables/).
  2. Clone repo from task 02.
  3. export variable for wordpress tag from `plugin_version`
  4. Export variable for the exposed port by wordpress on dev environment. For example: `81`
  5. Run `docker-compose in detached mode, so that you can log in to started wordpress blog.

#### 4.3. Run tests.

* Run the container with tests that you created for task 03 to test that the new plugin was successfully deployed on wordpress.

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

* Take your time to understand how Jenkins work.
* If you check out job configuration `scriptPath` it reads a file. This file is also called `Jenkinsfile`.
* After Jenkins creation there would be only one `z_seed_job` in the dashboard. To load all your pipelines you should run this job.
* To check your changes to any stage you need to commit and push your changes to the repo.
* If you make changes to job configuration (for example create a new `deploy_prod` pipeline) you need to commit and push your changes, then run `z_seed_job` manually.
* If you make changes to the job, you only need to commit and push changes to the repo and just manually trigger the `deploy_dev` job.


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
