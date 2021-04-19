---
title: Task 05. Split Wordpress components into different servers.
active: true
published: true
tags: "Phase1"
---

Some time have passed and online magazine having his readers and fans. People like to read and comment articles, everything is good. One day you realised that database eats more and more resources while application remain with same loading. Paul suggested you to split database and wordpress itself into different servers, so that components don't consume each others resources.
<!--more-->

## Task

* **Repository**: Fork [repository for task05](https://github.com/learningdevops-makvaz-com/phase01_task05) and clone forked repo.
* **Provision Wordpress** : Setup Wordpress same as you have done in previous task using ansible and vagrant, but this time you should have two VMs one `database` where MySQL would be running and second `wordpress` which would be accessed from browser.
* **Open ports**: Make sure that port 3306 on `database` is open for application in `wordpress` vm. 
* **Source code**: Create repository in GitHub and send moderators a link to check. Remember, that any person should be able to clone your repo, go to the directory, run command `vagrant up` and Wordpress and MySQL would be fulle configured.

### Additional tasks if you feel that it was too easy.
1. Check out Wordpress files structure. Where does it store plugins, themes, uploaded pictures.

### Tips:

* Vagrant allows you manipulating Virtual Machines. Check out Usefull links for more info. Feel free to google.
* You don't need to modify `Vagrantfile` to make it work properly. But you can experiment and change any settings that you want.

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* [WordPress](https://wordpress.org/download/)

### Usefull links:

* [Vagrant - multiple VMs](https://www.vagrantup.com/docs/multi-machine)
* [Ansible Quickstart](https://www.redhat.com/en/blog/system-administrators-guide-getting-started-ansible-fast?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW)
* [Ansible. Create reusable artifacts](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse.html)

### FAQ

* *N/A*
