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
* `transmission_logfile` - sets `--logfile`
* `transmission_rmem_max` - sets `net.core.rmem_max` kernel parameter
* `transmission_wmem_max` - sets `net.core.wmem_max` kernel parameter
* `transmission_user` - OS user which runs transmission-daemon
* `transmission_enable` - boolean to start and enable transmission-daemon on boot

Variables for `settings.json`

* `transmission_settings_dht_enabled` - dht-enabled
* `transmission_settings_lpd_enabled` - lpd-enabled
* `transmission_settings_utp_enabled` - lpd-enabled
* `transmission_settings_download_dir` - download-dir
* `transmission_settings_incomplete_dir` - incomplete-dir
* `transmission_settings_watch_dir` - watch-dir
* `transmission_settings_rpc_port` - rpc-port
* `transmission_settings_peer_port` - peer-port
* `transmission_settings_rpc_whitelist` - rpc-whitelist
* `transmission_settings_umask` - umask


Dependencies
------------

Collections:

* `ansible.builtin`
* `ansible.posix`

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

GPLv3

Author Information
------------------

Vladimir Vasilev
