---
title: Task 01. Linux administration. Install packages, start services, troubleshoot if something not working. VM on Virtualbox.
published: true
active: true
tags: "Phase1"
difficulty: 0
---

Here the story begins. You are working on video games magazine that wants to go digital (yes, only now in 2021) as a first SRE/DevOps guy, who helps right now with infrastructure. Paul, your manager asked you to prepare server to host new site.

<!--more-->

## Task

* Setup Ubuntu on Virtual Machive (Virtual Box)
* install and setup web server (nginx)
* create file `/var/www/html/index.html` with following content:

```html
<head>
<title>CyberGamer - best online magazine in the world</title>
</head>
<body>
<h1>CyberGamer - best online magazine in the world</h1>
</body>
```

* make sure that this page rendered correctly when you access your virtual machine ip address in browser.

### Additional tasks if you feel that it was too easy.
1. Make sure that you opened only needed ports
2. Know your software - make sure that you have installed stable and secure nginx version (no CVE found for this version)
3. Create self-signed certificate and setup HTTPS connection to your VM(Virtual Machine)

### Recommended soft:

* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Ubuntu](https://releases.ubuntu.com/20.04/ubuntu-20.04.2-live-server-amd64.iso)

### Useful links:

* [Install Ubuntu on VirtualBox](https://linuxhint.com/install_ubuntu_virtualbox_2004/#:~:text=Downloading%20Ubuntu%2020.04%20ISO%20Image%3A&text=Click%20on%20the%2064%2Dbit%20PC%20(AMD64)%20server%20install,The%20download%20should%20start.)

### FAQ
* n/a
