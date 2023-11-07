ansible-role-unit_config
=========

Creates overrides for existing systemd unit files.

Requirements
------------

The defined systemd unit file that you want to override must be already in place.

Role Variables
--------------

```
unit_config_enabled: false
```

Enable this explicitly on a host or group basis.

```
unit_item.type
```

Defaults to `.service` through the `_default_unit_type` variable. This will be added to the unit file name.

```
unit_config: []
```

See example for usage.


Dependencies
------------

No dependencies.

Example Playbook
----------------

```
- hosts: server
  become: true

  roles:
    - role: chrisvanmeer.unit_config
      vars:
        unit_config_enabled: true
        unit_config:
          - name: jira
            Unit:
              Before: ngninx.service
```

License
-------

BSD

