---
title: Task 06. Run wordpress with multiple application servers.
active: true
published: true
tags: "Phase1"
difficulty: 2
---

Paul, the CTO in your company is very interested in containers technology. You were asked to play with Docker. So in this task you need to setup custom application in container.
<!--more-->

## Task

* **Repository**: Fork [repository for task06](https://github.com/learningdevops-makvaz-com/phase01_task06) and clone forked repo.

* **Provision Wordpress** : Setup Wordpress using Ansible and Vagrant, but this time there would be 4 VMs:
  1. `database`, where MySQL is running
  2. 2 * `wordpress`, where nginx and php is running, it should point in configuration in `database` VM.
  3. `lb`, where Load balancer would redirect requests to both `wordpress` VMs. For load balancer you can use different programms on your choice: `nginx`, `apache-http`, `traefic` or any other.

* **Multimedia files always available**: After successfully deploying wordpress try to create new post with five different images. Try to refresh page 7 times. Make sure that every time page refreshed all pictures are visible.

* **Source code**: Create pull request to repository that you forked, so that you can get comments on your code.

### Additional tasks if you feel that it was too easy.
1. *N/A*

### Tips:

* Check out in internet what is the difference between vertical and horisontal scaling.
* Check out in internet what types of load balancers and their features, like session stickiness.

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* [WordPress](https://wordpress.org/download/)
* [WP-cli](https://wp-cli.org/)

### Useful links:

* [Vagrant - multiple VMs](https://www.vagrantup.com/docs/multi-machine)
* [Ansible Quickstart](https://www.redhat.com/en/blog/system-administrators-guide-getting-started-ansible-fast?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW)
* [Ansible. Create reusable artifacts](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse.html)

### FAQ

* *N/A*
