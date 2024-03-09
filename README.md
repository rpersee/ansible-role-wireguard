WireGuard Ansible Role
======================

WireGuard containerized deployment in Podman with [linuxserver/wireguard](https://github.com/linuxserver/docker-wireguard) image.

Requirements
------------

Password-less SSH access to the server is required when deploying in client mode, to fetch the peer configuration.

Role Variables
--------------

See [`defaults/main.yml`](https://github.com/rpersee/ansible-role-wireguard/blob/main/defaults/main.yml) for the settable variables for this role.  
You can find a description of the variables in the [linuxserver/wireguard documentation](https://docs.linuxserver.io/images/docker-wireguard#parameters).

When deploying in client mode, you should set:
- `server_user` and `server_host` to access the server with the peer configuration
- `peer_id` to select the peer configuration to fetch from the server

Dependencies
------------

You might need to install collections from `requirements.yml` if they don't come with your Ansible installation.

Example Playbook
----------------

To deploy in server mode:

```yaml
- hosts: all
  roles:
      - { role: rpersee.wireguard, mode: server }
```

License
-------

GNU Affero General Public License v3.0 or later
