---
title: Task 04. Deploy on Kubernetes using helm and kustomize.
published: true
active: true
tags: "Phase3"
difficulty: 2
---

You were able to successfully run wordpress in Kubernetes. Now it's time to make wordpress setup configurable.

<!--more-->

## Task

### 1. Repository

- Fork [repository for task03](https://github.com/learningdevops-makvaz-com/phase03_task04) and clone forked repo.

### 2. Understand helm basics.

- **Learn about how to use [Helm](https://helm.sh/docs/intro/using_helm/)**: read documentation
- **Run nginx chart with some changes**: Install into your kubernetes cluster [nginx chart](https://artifacthub.io/packages/helm/bitnami/nginx) with release name `my-nginx` and following changes: `replicaCount` set to 3.
- **Fix service type**: It seems that `LoadBalancer` service type is not proper in our case. Please [upgrade](https://helm.sh/docs/helm/helm_upgrade/) release to use service type as `NodePort`. Don't forget to to keep number of replicas as `3`. 
- **Check that application is working correctly**: try to access `my-nginx` service 80th port and make sure that nginx is running. You can also check logs on different pods.
- **Cleanup**: delete `my-nginx` release from cluster.

### 3. Create your own helm chart.

- **Create your own chart that installs wordpress**: Using manifests from previous task that brings up database and application create template for new helm chart in `helm` folder.
- **Make some paramters configurable**:
  - requests and limits
  - app label value
  - version of thank-after-post plugin that is downloaded in init container

- **Create github workflow that saves your chart on push to master/main branch**

### 4. Run local WordPress setup in couple pods using Deployment.

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

- [Creating helm template](https://helm.sh/docs/chart_template_guide/getting_started/)
- [Kuberentes Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [Kubernetes Service](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Kubernetes StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)

### FAQ

- _N/A_
