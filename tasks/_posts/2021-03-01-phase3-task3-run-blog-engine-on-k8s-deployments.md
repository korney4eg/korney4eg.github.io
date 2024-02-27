---
title: Task 03. Run WordPress on kubernetes using Deployment, StatefulSet, Service.
published: true
active: true
tags: "Phase3"
difficulty: 2
---

Now it's time to scale your application to be able to handle load. So you decided to use deployments, services, statefulsets in your blog engine.

<!--more-->

## Task

### 1. Repository

- Fork [repository for task03](https://github.com/learningdevops-makvaz-com/phase03_task03) and clone forked repo.

### 2. Run local WordPress setup in couple pods using Deployment.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p2.png)
{: refdef}

- Create Deployment with following parameters:
  - replicas: `3`
  - pods labels `app: wordpress`
  - container port should be `80`
  - image for wordpress container should be `korney4eg/wordpress-empty:latest`
  - pods selector should look for pods labeled `app: wordpress`
  - pod name: `wordpress`

- **Run MySQL database inside container `database` in pod `wordpress`**: Update `wordpress_manifest.yaml` so that there would be pod `wordpress` with `database` container that listens on port `3306`. Feel free to hard-code password and other parameters should  into manifest. To verify that database is working properly try to run expose database port using `kubectl port-forward` command.
- **Run Wordpress inside container `app` in pod `wordpress`**: Update `wordpress_manifest.yaml` by adding `app` container that listens on port `80` and accessing database by address `localhost:3306`. Use password and other parameters that you configured in previous step.
- **Check that wordpress pod is running**.
- **Clean up**: Run command `kubectl delete -f wordpress_manifest.yaml`.

### 3. Run local MySQL database with StatefulSet.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p3.png)
{: refdef}

- **Run pod `database` with MySQL database container**: Update `database.yaml` so that there would be pod `database` with `mysql` container that works on port `3306`. Password and other parameters should be hard-coded in manifest.
- **Check that `database` pod is running**. Try to use Kubernetes service.
- **Run pod with Wordpress**: Update `wordpress.yaml` so that there would be pod `wordpress` with `app` container that works on port `80`. Password and other parameters should be hard-coded in manifest. Use `database` pod's address as your database.
- **Check that wordpress pod is running**. Try to use Kubernetes service.
- ** Clean up**: Run command `kubectl delete -f wordpress_manifest.yaml`.

### 4. Run Init container inside WordPress pod.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p4.png)
{: refdef}

- **Build container with wordpress that doesn't have plugin built it**.
- **Replace container image from `app` container with newly built image**.
- **Run Init container `plugin-download` that downloads plugin**: Before `app` container started we need to have [thank-after-post-plugin](https://github.com/korney4eg/thank-after-post-plugin) to be downloaded by `plugin-download` container and later to be mounted in `app` container. Please update `wordpress.yaml` file for this task.

### 5. Make your work visible.

Create Pull Request with changes on files:

- `wordpress_manifest.yaml`
- `database.yaml`
- `wordpress.yaml`

### Additional tasks if you feel that it was too easy.

1. Resources and limits: Before running any container it's always nice to limit it's resources usage so that it doesn't allocate all of them. Try to use it.
2. Kubernetes has mechanism to check whether container is ready to handle traffic, it's called `readinessProbe`. Try to use it.
3. Kubernetes has mechanism to check whether container is ready to handle traffic, it's called `livenessProbe`. Try to use it.

### Tips:

- _N/A_

### Recommended soft:

- _N/A_

### Useful links:

- [Kuberentes API](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.22/)
- [Kuberentes Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

### FAQ

- _N/A_