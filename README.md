Role
====
Docker install : Install and configure docker

Requirements
------------
ansible 2.1

Role Vars
---------
### Storage drivers (Ubuntu only)
```yaml
    docker_aufs: true
```
### Kernel modules (Ubuntu only)
```yaml
    kernel_modules:
      - aufs
      - configfs
```
### Storage drivers (CentOS only)
```yaml
    docker_direct_lvm: true
    docker_volume_group: "docker"
```
Dependencies
------------
Ansible 2.0


Playbook examples
-----------------

```yaml
    - hosts: ubuntu-server
      roles:
        - role: ansible-docker-install
          docker_aufs: true
```

```yaml
    - hosts: centos-server
      roles:
        - role: ansible-docker-install
          docker_direct_lvm: true
          docker_volume_group: "vgdodock"
```

Distrib Support
---------------
| Distribution | Compat | Test  |
| ------------ |:------:|:-----:|
|    CentOS 7  |   Y    |   Y   |
| Ubuntu 16.04 |   Y    |   Y   |


TODO
----
* Debian compat
* More storage drivers (aufs: done, direct lvm: done)
