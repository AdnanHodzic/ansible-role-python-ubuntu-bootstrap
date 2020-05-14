Ansible Role: Install Python on newly bootstrapped Ubuntu host
=========

**Install Python on newly bootstrapped Ubuntu or Debian host**

This Ansible role will install Python on newly bootstrapped host. This is usually
a new host which you never even SSH-ed to.

In order for Ansible to work, Python must be installed (if missing).

This role was created as part of [containerized-wordpress-project](https://github.com/AdnanHodzic/containerized-wordpress-project)

Requirements
------------

None.

Role Variables
--------------

Unless you don't want `gather_facts: yes` to be set and enabled as second part of the playbook. 
Make sure to comment/delete following line from `tasks/main.yml`

```- setup: # aka gather_facts: yes```

See [Example Playbook](https://github.com/AdnanHodzic/ansible-role-python-ubuntu-bootstrap#example-playbook) section for more information


Dependencies
------------

None.

Example Playbook

This role was created to be run as part of pre_tasks, i.e:
----------------

```
# run as part of pre_tasks
- hosts: servers
  remote_user: ubuntu
  become: yes
  gather_facts: no
  serial: 1

  roles:
    - { role: AdnanHodzic.python-ubuntu-bootstrap }

- hosts: servers
  remote_user: ubuntu
  become: yes

# run as part of tasks
  roles:
    ...
```

License
-------

GPLv3

Donate
-------

Since I'm working on this project in free time, please consider supporting this project by making a donation of any amount!

##### PayPal
[![paypal](https://www.paypalobjects.com/en_US/NL/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=7AHCP5PU95S4Y&item_name=Contribution+for+work+on+containerized-wordpress-project&currency_code=EUR&source=url)

##### BitCoin
[bc1qlncmgdjyqy8pe4gad4k2s6xtyr8f2r3ehrnl87](bitcoin:bc1qlncmgdjyqy8pe4gad4k2s6xtyr8f2r3ehrnl87)

[![bitcoin](https://foolcontrol.org/wp-content/uploads/2019/08/btc-donate-displaylink-debian.png)](bitcoin:bc1qlncmgdjyqy8pe4gad4k2s6xtyr8f2r3ehrnl87)
