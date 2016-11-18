Role
====
Docker install : Install and configure docker

Requirements
------------
ansible 2.1

Role Vars
---------
### Storage drivers
```yaml
    docker_aufs: yes
```
### Kernel modules
```yaml
    kernel_modules:
      - aufs
      - configfs
```
Dependencies
------------
None


Playbook examples
-----------------
```yaml
    - hosts: all
      become: yes
      roles:
        - ansible-docker-install
```

```yaml
    - hosts: all
      become: yes
      roles:
        - { role: ansible-docker-install, docker_aufs: true }
```

Distrib Support
---------------
| Distribution | Compat | Test  |
| ------------ |:------:|:-----:|
|    CentOS 7  |   N    |   N   |
| Ubuntu 16.04 |   Y    |   Y   |


TODO
----
* CentOS compat
* Debian compat
* More storage drivers
* Some checks
