Ansible - custom
=========

Manage custom stuffs with Ansible:

- some OS settings (`issue`, `issue.net`,`motd` files)
- timezone
- packages

Requirements
------------

NA

Role Variables
--------------

```yaml
# os setting:
# No necessary variable, automatic generate from issue template file.

# timezone
# Only necessary a custom_timezone_name variable.
custom_timezone_hwclock: "UTC"
custom_timezone_name: "Europe/London"

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

- [community.general.timezone](
https://docs.ansible.com/ansible/latest/collections/community/general/timezone_module.html#ansible-collections-community-general-timezone-module
)
- [community.general.apk](
https://docs.ansible.com/ansible/latest/collections/community/general/apk_module.html
) (for package module)

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
