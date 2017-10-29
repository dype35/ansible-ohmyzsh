OhMyZsh
=======

[![Build Status](https://travis-ci.org/jebovic/ansible-ohmyzsh.svg?branch=master)](https://travis-ci.org/jebovic/ansible-ohmyzsh) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.ohmyzsh-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/ohmyzsh)

Install and configure Oh My Zsh for multiple users

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Requirements
------------

Need zsh to be installed first

Role Variables
--------------

```yaml
# Choose user who you want to install oh my zsh for
ohmyzsh_users:
  - username: ops
    usergroup: admin
    home: /home/ops
  - username: root
    usergroup: root
    home: /root

ohmyzsh_plugins: git colored-man-page colorize extract history composer zsh-syntax-highlighting
ohmyzsh_theme: bira
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.ohmyzsh }
```

Example : config
----------------

```yaml
# Configure oh-my-zsh for your user
ohmyzsh_users:
  - username: me
    usergroup: me
    home: /home/me
ohmyzsh_plugins: git colored-man-page colorize extract history zsh-syntax-highlighting
ohmyzsh_theme: bira
```

Tags
----

* ohmyzsh_config : only update config

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
