---
title: Task 04. Using Ansible to configure Wordpress on VirtualBox.
published: true
active: true
tags: "Phase1"
heroes:
  - '[@dbemol](https://www.reddit.com/user/dbemol/)'
  - '[Devan](https://github.com/devanbenz)'
  - '[Maverick](https://twitter.com/rojintheone)'
difficulty: 2
---


One day you were on local DevOps conference and one guy talked about Configuration Management on laptop, using Vagrant and Ansible. He mentioned that Vagrant allows you configure and operate virtual machines using only command line and Ansible allows you configure all you need. You were so excited about that new things, so after comming home you wanted to try Vagrant and Ansible yourself and asked guy from conference to send you example. He sent you a [link to the repo on GitHub](https://github.com/learningdevops-makvaz-com/phase01_task04) and asked to fork it.
<!--more-->

## Task

* **Repository**: Fork [repository](https://github.com/learningdevops-makvaz-com/phase01_task04) and clone forked repo.
* **Create VM** : using Vagrant start configured VM `wordpress`. Try to provision it. Destroy, recreate.
* **Configuration Management** : update ansible playbook `wordpress.yaml` that installs, configures and starts nginx, mysql, WordPress. WordPress should have already configured with theme [twentynineteen](https://ru.wordpress.org/themes/twentynineteen/) and with created user `admin` with password `!2three456.`.
* **Contribute**: After wordpress is configured using ansible push all your changes to the forked repo and create pull request.
* **Check yourself**: 
  1. Create VM using Vagrant for the first time that should trigger provision.
  2. You should be able to open [http://192.168.50.2](http://192.168.50.2) in your browser and see preconfigured theme and user already created.
  3. Login as `admin` user and create new blogpost.
  4. Run provision on VM using Vagrant.
  5. In browser after refreshing page you should still see your blogpost.
  6. If you completed previous task you could mentioned the difference between script and Configuration Management tool. Try to list all the differences between them.

### Additional tasks if you feel that it was too easy.
1. You can write down everything to one file, but usually it make sence to group tasks into the roles and include roles to ansible playbooks. Try to split your big yaml file to roles and reuse them.

### Tips:

* Vagrant allows you manipulating Virtual Machines. Check out Useful links for more info. Feel free to google.
* You don't need to modify `Vagrantfile` to make it work properly. But you can experiment and change any settings that you want.
* Changing WordPress settings much easier using `wp-cli` tool.

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* [WordPress](https://wordpress.org/download/)
* [WP-cli](https://wp-cli.org/)

### Useful links:

* [Ansible in Vagrant](https://www.vagrantup.com/docs/provisioning/ansible_intro)
* [Vagrant quickstart](https://learn.hashicorp.com/tutorials/vagrant/getting-started-index?in=vagrant/getting-started)
* [Ansible Quickstart](https://www.redhat.com/en/blog/system-administrators-guide-getting-started-ansible-fast?extIdCarryOver=true&sc_cid=701f2000001OH7YAAW)

### FAQ

* *N/A*
