---
title: Task 01. Start Kubernetes locally.
published: true
active: true
tags: "Phase3"
difficulty: 1
---

Looking in the near future and seeing that kubernetes becomes started for container orchestration tool you decided to learn more about it and later to migrate blog into this platform.

As a first step you decided to run Kubernetes locally on your computer.

<!--more-->

## Task

- **Install kubernetes in docker**: Follow instructions from [documentation](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)
- **Run pod with nginx container**: Start new pod with nginx container and make sure that it's running.
- **Check logs of nginx container**
- **Make port forwarding of nginx pod**: Try to access nginx inside pod using your web browser and tools provided by kubernetes.
- ** Check resources used by nginx pod**: Try to find kubernetes command that will allow you to see resource usage by pod.
- **get information of when did pod started**
- **remove nginx pod**

### Additional tasks if you feel that it was too easy.

1. Setup dashboard to see kubernetes and pods info inside your browser.

### Tips:

- Create alias for `kubectl` command as `k` to faster typing. [documentation](https://v1-18.docs.kubernetes.io/docs/reference/kubectl/cheatsheet/#kubectl-autocomplete)
- Check out kubernetes resources using great console tool called [`k9s`](https://github.com/derailed/k9s)
- To easily switch between contexts(profiles) use [`kubectx`](https://github.com/ahmetb/kubectx)

### Recommended soft:

- [kubernetes in docker](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)
- [`kubectx`](https://github.com/ahmetb/kubectx)
- [`k9s`](https://github.com/derailed/k9s)
- [docker](https://www.docker.com/get-started)

### Useful links:

- [Kubernetes getting started](https://kubernetes.io/docs/setup/)

### FAQ

- _N/A_
