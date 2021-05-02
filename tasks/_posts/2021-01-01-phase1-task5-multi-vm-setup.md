---
title: Task 05. Split Wordpress components into different servers.
active: true
published: true
tags: "Phase1"
difficulty: 1
---

Some time have passed and online magazine having his readers and fans. People like to read and comment articles, everything is good. One day you realised that database eats more and more resources while application remain with same loading. Paul suggested you to split database and wordpress itself into different servers, so that components don't consume each others resources.
<!--more-->

## Task

* **Repository**: Fork [repository for task05](https://github.com/learningdevops-makvaz-com/phase01_task05) and clone forked repo.
* **Provision Wordpress** : Setup Wordpress using Ansible and Vagrant, but this time there would be two VMs:
  1. `database`, where MySQL is running
  2. `wordpress`, where nginx and php is running, it should point in configuration in `database` VM.
* **Open ports**: Make sure that port 3306 on `database` is open for application in `wordpress` vm. 
* **Source code**: Create pull request to repository that you forked, so that you can get comments on your code.
* **Think yourself**: While it's easy to copy something from the internet, I would recommend writing roles and tasks writing from scratch, or reuse from previous task. In that case you would learn more.

### Additional tasks if you feel that it was too easy.
1. Check out Wordpress files structure. Where does it store plugins, themes, uploaded pictures. You will need this in future tasks.

### Tips:

* Vagrant allows you manipulating Virtual Machines. Check out Useful links for more info. Feel free to google.
* You don't need to modify `Vagrantfile` to make it work properly. But you can experiment and change any settings that you want.
* Changing WordPress settings much easier using `wp-cli` tool.
* Ansible allows to group tasks in to the roles.

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
