---
title: Advanced shell scripting.
published: true
active: true
tags: "Phase1"
heroes:
  - '[@dbemol](https://www.reddit.com/user/dbemol/)'
difficulty: 3
---

You probably know programm [ps](https://man7.org/linux/man-pages/man1/ps.1.html), that allow to see a lot of information about given process. Your task would be to write bash script `proc_info.sh` that will get `pid` (process id) and shows following information:

<!--more-->

* who run this process
* what command was used to run process
* what environment variables this process knows
* what files curretrly open by this process

Fork repo https://github.com/learningdevops-makvaz-com/phase01_adv_shell_scripting and use this code.

All this information you need to get without using `ps`, `*top`, `lsof` or any other system programms.

## Tips

* Check out how to make bash script work with arguments
* Check out Linux filesystem structure
