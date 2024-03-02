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
- **Run simple application in deployment from file**: Create deployment using yaml file `wordpress_manifest.yaml`, with name `simple-app` that would run `dockersamples/static-site` container, has label `app: simple-app` and has `2` replicas, exposed port 80. Apply your changes to kubernetes. And using `kubectl port-forward` command try to open you application in browser.
- **Run simple application in deployment using command line**: Create deployment using command `kubectl run`, with name `simple-app2` that would run `dockersamples/static-site` container, has label `app: simple-app2` and has `2` replicas, exposed port 80. Apply your changes to kubernetes. And using `kubectl port-forward` command try to open you application in browser.

- **Learn about Kubernetes [Service](https://kubernetes.io/docs/concepts/services-networking/service/)**: read documentation
- **Expose simple-app pods as one endpoint**: After creating and properly configuring service make sure that application is available on this service.
- **Clean up**: remove created previously deployments and service.

### 2. Run local MySQL database with StatefulSet.

- **Learn about Kubernetes [StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)**
- **Create StatefulSet database**: Create statefulSet named `database`, with container `mysql`, with labels that you want. Add it to `database.yaml` file.
- **Expose database using service**. Make sure that MySQL is accessible by port 3306. Add it to `database.yaml` file.

### 3. Run local WordPress setup in couple pods using Deployment.

- **Create Deployment with following parameters:**
  - deployment name: `wordpress`
  - replicas: `2`
  - pods labels `app: wordpress`
  - use `wordpress` pod manifest from previous task as a template for deployment
  - save manifest to `wordpress.yaml` file

- **Expose wordpress using service**. Make sure that Wordpress blog is accessible by port 80. Add it to `wordpress.yaml` file.

### 4. Make your work visible.

Create Pull Request with changes on files:

- `wordpress_manifest.yaml`
- `database.yaml`
- `wordpress.yaml`

### 5. Cleanup created resources

### Additional tasks if you feel that it was too easy.

- _N/A_

### Tips:

- _N/A_

### Recommended soft:

- _N/A_

### Useful links:

- [Kuberentes API](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.22/)
- [Kuberentes Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [Kubernetes Service](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Kubernetes StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)

### FAQ

- _N/A_
