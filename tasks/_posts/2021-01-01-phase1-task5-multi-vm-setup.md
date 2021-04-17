---
title: Task 05. Split Wordpress components into different servers.
active: true
published: true
tags: "Phase1"
---

Some time have passed and online magazine having his readers. People like to read and comment articles, all is good. One day you realised that database eats more and more resources while application remain with same loading. Paul suggested you to split database and wordpress itself into different servers, so that components don't consume each others resources.
<!--more-->

## Task

* **Provision Wordpress** : Setup Wordpress same as you have done in previous task using ansible and vagrant, but this time you should have two VMs one `database` where MySQL would be running and second `wordpress` which would be accessed from browser.
* **Open ports**: Make sure that port 3306 on `database` is open for application in `wordpress` vm. 
* **Source code**: Create repository in GitHub and send moderators a link to check. Remember, that any person should be able to clone your repo, go to the directory, run command `vagrant up` and Wordpress and MySQL would be fulle configured.

### Additional tasks if you feel that it was too easy.
1. Automate VM manipulation with [Vagrant](https://www.vagrantup.com/downloads). It will allow you to configure everything in the code. Set VM parameters in `Vagrantfile`.
2. Try to rewrite your script to make it work every time you run it with new VM and VM with already setup WordPress, so it 

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
