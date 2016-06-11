nolith.docker
=============

The way I run docker.

Role Variables
--------------

This role defines the following variables:

```yml
docker_cfg: docker.cfg
docker_cfg_dest: /etc/default/docker
docker_extra: ""
docker_users: []
```

It also expects to read `ansible_distribution`, `ansible_distribution_release`
and `ansible_distribution_major_version` in order to detect systemd based OS.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- hosts: servers
  roles:
    - role: nolith.docker
      docker_users: [frank, joe, mark]
      docker_extra: --dns 8.8.8.8 --dns 8.8.4.4
```

License
-------

MIT
