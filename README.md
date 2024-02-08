Ansible - custom
=========

Manage custom stuffs with Ansible:

- some OS settings (`issue`, `issue.net`,`motd` files)
- packages
- `sysctl`

Requirements
------------

NA

Role Variables
--------------

```yaml
# os setting:
# No neccessary variable, automatic generate from issue template file.

# package
# Install all package from `custom__package_.+` merged list.
custom__package_all:
  - openssh
custom__package_group:
  - vim
custom__package_webserver:
  - nginx
custom__package:
  - syslog
```

> And see `default/main.yml` file.

Dependencies
------------

- [community.general.apk](https://docs.ansible.com/ansible/latest/collections/community/general/apk_module.html) (for package module)

Example Playbook
----------------

```yaml
 - hosts: servers
   roles:
     - { role: custom, tags: [ custom ] }
```

License
-------

GPLv3
