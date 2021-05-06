---
title: Task 06. Run wordpress with multiple application servers.
active: true
published: true
tags: "Phase1"
difficulty: 2
heroes:
  - '[@dbemol](https://www.reddit.com/user/dbemol/)'
---

After splitting up database and application load on servers decreased for some time. You were happy that you can separately operate on each server. One night on your server with wordpress - application server, logs felt all the disc space and web site wasn't working. Paul was not very happy about it, but as he was experienced, he knew that we learn faster on failures. He asked if you heard anything about vertical and horizontal scaling and advised you to read about it and make Magazine more reliable so if one server fails, the other keeps working.
<!--more-->

## Task

* **Repository**: Fork [repository for task06](https://github.com/learningdevops-makvaz-com/phase01_task06) and clone forked repo.

* **Provision reliable Wordpress** : Setup Wordpress using Ansible and Vagrant, but this time there would be 4 VMs:
  1. `database`, where MySQL is running
  2. 2 * `wordpress`, where nginx and php are running, it should point in a configuration in `database` VM.
  3. `lb`, where Load balancer would redirect requests to both `wordpress` VMs. For load balancer you can use different programs of your choice: `nginx`, `apache-http`, `traefik`, or any other.

* **Multimedia files always available**: After successfully deploying wordpress try to create a new post with five different images. Try to refresh the page 7 times. Make sure that every time page is refreshed all pictures are visible.

* **Source code**: Create a pull request to the repository that you forked, so that you can get comments on your code.

### Additional tasks if you feel that it was too easy.
1. *N/A*

### Tips:

* Check out on the internet what is the difference between vertical and horizontal scaling.
* Check out on the internet what types of load balancers and their features, like session stickiness.

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* [WordPress](https://wordpress.org/download/)
* [WP-cli](https://wp-cli.org/)

### Useful links:

* [Scaling Horizontally vs. Scaling Vertically](https://www.section.io/blog/scaling-horizontally-vs-vertically/)
* [Sticky and nonsticky sessions](https://stackoverflow.com/questions/10494431/sticky-and-non-sticky-sessions)
* [Vagrant - multiple VMs](https://www.vagrantup.com/docs/multi-machine)
* [Ansible Quickstart](https://www.redhat.com/en/blog/system-administrators-guide-getting-started-ansible-fast?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW)
* [Ansible. Create reusable artifacts](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse.html)

### FAQ

* *N/A*
