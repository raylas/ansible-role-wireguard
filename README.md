Ansible Role: WireGuard
=========

Installation and basic provisioning of [WireGuard](https://www.wireguard.com) on RedHat and Ubuntu hosts.

Requirements
------------

A RedHat or Ubuntu host in your inventory.

Role Variables
--------------

Default variables:
```
wg_conf_template: 'wg0.conf.j2'
wg_conf_file_path: '/etc/wireguard/wg0.conf'
wg_listen_port: 51820
```
**Required**: Specify source template and destination file path for the WireGuard configuration file. Also specify the local WireGuard listen port.

Host variables:
```
wg_local_address: '10.0.1.5/32'
wg_private_key: '43kfsmvir...'

wg_peers:
  - name: 'host1'
    public_key: 'h+xMzv8ry7XO...'
    endpoint: '10.0.2.5:12800'
    keep_alive: 25
    allowed_ips: '10.0.2.0/24'
```
**Required**: At minimum, define these variables per-host in your inventory that utilized the WireGuard role.


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
- name: Configure WireGuard mesh
  hosts: all
  become: yes

  roles:
    - wireguard
```

License
-------

MIT

Author Information
------------------

This role was created in 2020 by [Raymond Douglas](https://rymnd.org).
