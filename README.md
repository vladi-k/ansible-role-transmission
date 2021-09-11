ansible-role-transmission
=========

Install and configure Transmission BitTorrent client.

Requirements
------------

YUM repository with transmission (like EPEL)

Role Variables
--------------

* `transmission_packages` - list of packages to install
* `transmission_exec_start` - ExecStart part of transmission systemd service
* `transmission_allowed_ips` - list of IPs to set `rpc-whitelist`
* `transmission_watch_dir` - sets `watch-dir`
* `transmission_incomplete_dir` - sets `incomplete-dir`
* `transmission_rpc_bind_address` - sets `rpc-bind-address`
* `transmission_dht` - boolean to set `dht`
* `transmission_port` - sets `rpc-port`
* `transmission_peerport` - sets `peer-port`
* `transmission_utp` - boolean to set `utp`
* `transmission_lpd` - boolean to set `lpd`
* `transmission_download_dir` - sets `download-dir`
* `transmission_logfile` - sets `--logfile`
* `transmission_user` - OS user which runs transmission-daemon
* `transmission_enable` - boolean to start and enable transmission-daemon on boot


Dependencies
------------

Collections:

* `ansible.builtin`

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    transmission_watch_dir: /mnt/torrents/0_NEW
    transmission_incomplete_dir: /mnt/torrents/z_incomplete
    transmission_download_dir: /mnt/torrents
  roles:
    - ansible-role-transmission
```

License
-------

BSD

Author Information
------------------

Vladimir Vasilev
