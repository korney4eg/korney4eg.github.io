---
title: Task 02. Run blog engine on k8s. Pods.
published: true
active: true
tags: "Phase3"
difficulty: 2
---

### Kubernetes pods.

Here would be first lesson.

<!--more-->

## Task

### 1. Repository

- Fork [repository for task02](https://github.com/learningdevops-makvaz-com/phase03_task02) and clone forked repo.

### 2. Run local WordPress setup in single pod.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p2.png)
{: refdef}

- **Run pod with MySQL database**: Update `wordpress_manifest.yaml` so that there would be pod `wordpress` with `database` container that listens on port `3306`. Password and other parameters should be hardcoded in manifest.
- **Run `app` container with Wordpress in the same pod**: Update `wordpress_manifest.yaml` so that there would be pod `wordpress` with additional `app` container that listens on port `80` and accessing database by address `localhost:3306`. Password and other parameters should be hardcoded in manifest.
- **Check that wordpress pod is running**.

### 3. Run local WordPress setup in multiple pods.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p3.png)
{: refdef}

- **Run pod with MySQL database**: Update `database.yaml` so that there would be pod `database` with `mysql` container that works on port `3306`. Password and other parameters should be hardcoded in manifest.
- **Check that `database` pod is running**.
- **Run pod with Wordpress**: Update `wordpress.yaml` so that there would be pod `wordpress` with `app` container that works on port `80`. Password and other parameters should be hardcoded in manifest. Use `database` pod's address as your database.
- **Check that wordpress pod is running**.

### 4. Run Init container inside WordPress pod.

{:refdef: style="text-align: center;"}
![Diagramm](assets/ph3_t2_p4.png)
{: refdef}

- **Build container with wordpress that doens't have plugin built it**.
- **Replace container image from `app` container with newly built image**.
- **Run Init container `plugin-download` that downloads plugin**: Before `app` container started we need to have [thank-after-post-plugin](https://github.com/korney4eg/thank-after-post-plugin) to be downloaded by `plugin-download` container and later to be mounted in `app` container. Please update `wordpress.yaml` file for this task.

### 5. Make your work visible.

Create Pull Request with changes on files:

- `wordpress_manifest.yaml`
- `database.yaml`
- `wordpress.yaml`

### Additional tasks if you feel that it was too easy.

1. Resources and limits: Before running any container it's always nice to limit it's resources usage so that it doesn't allocate all of them. Try to use it.
2. Kubernetes has mechanism to check whether container is ready to handle traffick, it's called `readinessProbe`. Try to use it.
3. Kubernetes has mechanism to check whether container is ready to handle traffick, it's called `livenessProbe`. Try to use it.

### Tips:

- _N/A_

### Recommended soft:

- _N/A_

### Useful links:

- [Kuberentes API](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.22/)
- [Kuberentes Pods](https://kubernetes.io/docs/concepts/workloads/pods/)

### FAQ

- _N/A_
