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

### 2. Understand Kubernetes basics.

- **Learn about Kubernetes [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)**: read documentation
- **Run simple application in deployment from file**: Create deployment using yaml file, with name `simple-app` that would run `dockersamples/static-site` container, has label `app: simple-app` and has `2` replicas, exposed port 80. Apply your changes to kubernetes. And using `kubectl port-forward` command try to open you application in browser.
- **Run simple application in deployment using command line**: Create deployment using command `kubectl run`, with name `simple-app2` that would run `dockersamples/static-site` container, has label `app: simple-app2` and has `2` replicas, exposed port 80. Apply your changes to kubernetes. And using `kubectl port-forward` command try to open you application in browser.

- **Learn about Kubernetes [Service](https://kubernetes.io/docs/concepts/services-networking/service/)**: read documentation
- **Expose simple-app pods as one endpoint**: After creating and properly configuring service make sure that application is available on this service.
- **Clean up**: remove created previously deployments and service.

### 2. Run local MySQL database with StatefulSet.

- **Learn about Kubernetes [StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)**
- **Create StatefulSet database**: Create statefulSet named `database`, with container `mysql`, with labels that you want.
- **Expose database using service**. Make sure that MySQL is accessible by port 3306.

### 3. Run local WordPress setup in couple pods using Deployment.

- Create Deployment with following parameters:
  - replicas: `2`
  - pods labels `app: wordpress`
  - container port should be `80`
  - image for wordpress container should be `korney4eg/wordpress-empty:latest`
  - pods selector should look for pods labeled `app: wordpress`
  - pod name: `wordpress`

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
