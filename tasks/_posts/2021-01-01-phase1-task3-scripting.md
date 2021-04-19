---
title: Task 03. Scripting. Automate installation of WordPress.
published: true
active: true
tags: "Phase1"
---

Authors want to try out new blogging platform. They asked you to install and setup WordPress for everyone. Suddenly you realised that there are already 30 editors working in online magazine "GamePlayer". You hear behind your back Paul's voice: "You can do it 30 times or you can write once and run anytime you want".
<!--more-->

## Task

* **Repository**: Fork [repository](https://github.com/learningdevops-makvaz-com/phase01_task03) and clone forked repo.
* **Create VM** : using Vagrant start configured VM `wordpress`. Try to provision it. Destroy, recreate.
* **Automate deployment** : edit bash script `setup_wordpress.sh` that installs, configures and starts nginx, mysql, WordPress. WordPress should have already configured with theme [twentynineteen](https://ru.wordpress.org/themes/twentynineteen/) and with created user `admin` with password `!2three456.`.
* Save changes on forked repo and share it. GitHub is most popular place to store code in the internet. For it you need to learn `git`. Git - is version control system, it allows you to store all history of your code. Git is used practically everywhere.

### Additional tasks if you feel that it was too easy.
1. Try to rewrite your script to make it work every time you run it with new VM and VM with already setup WordPress, so it 

### Tips:

* Bash script - is just a list of commands that will be run one after another. Here you will find magic of automation.
* Changing wordpress settings from Web UI it's easy. If you want to do it from bash script you should find tools that allows you to run them from command line. You can search in internet for "cli tool for wordpress", it should find something usefull.

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Ubuntu](https://releases.ubuntu.com/20.04/ubuntu-20.04.2-live-server-amd64.iso)
* [WordPress](https://wordpress.org/download/)

### Usefull links:

* [Bash scripting](https://medium.com/sysf/bash-scripting-everything-you-need-to-know-about-bash-shell-programming-cd08595f2fba)

### FAQ

* *N/A*
