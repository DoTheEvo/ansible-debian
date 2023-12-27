# Ansible Debian

![Logo](https://i.imgur.com/yAyr3S2.png)

Debian variation of my [ansible-arch](https://github.com/DoTheEvo/ansible-arch)

# Overview

The objective is to have an easy way to have fresh Debian installation setup
the way one desires. Reliably and with the least amount of effort.
For this Ansible is used.

Ansible is an automation platform.<br>
It executes tasks from `playbooks` on machines listed in `inventory`.
Open source, developed by Red Hat.
Written and dependent on python. Uses YAML configuration files.
Agent-less, controlled machines need just ssh+python (linux) or
winrm+powershell (windows).<br>
Praised for simplicity.

This repo aims to be easily customizable, playbooks being as simple as possible.
One should be able to look at them, see how stuff is done and make own changes.

# How to execute

install Debian, log in to a non root account that can sudo

* install ansible and git<br>
  `sudo apt install ansible git python-is-python3`
*  clone this repo<br>
  `git clone https://github.com/DoTheEvo/ansible-debian.git`
* enter the directory<br>
  `cd ansible-debian`
* run the playbooks you want
    * `ansible-playbook -u $USER -K playbook_core.yml`
    * `ansible-playbook -u $USER -K playbook_zsh.yml`
    * `ansible-playbook -u $USER -K playbook_docker.yml`
    * `ansible-playbook -u $USER -K playbook_caddy_kuma_ntfy.yml`

yes, you write `$USER` there, which puts in the user you are logged in <br>
the `-K` is short for `--ask-become-pass` which will prompt for password

**Removal**<br>
After running playbooks it be good to remove ansible package
and bunch of its dependencies. Saves \~600MB and noise during updates.

* `sudo apt remove ansible ansible-core`

