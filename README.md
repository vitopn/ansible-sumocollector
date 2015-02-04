Role Name
=========

Ansible role to install SumoCollector.

Role Variables
--------------

Default variables:

```
sumologic_installer_remote_file: /tmp/sumo.deb
sumocollector_installer_download: ""
sumologic_collector_accessid: ""
sumologic_collector_accesskey: ""
sumologic_collector_clobber: ""
sumologic_installer_file: ""
sumologic_collector_source_template: "collector.json.j2"
sumologic_collector_timezone: "UTC"
sumologic_collector_force_timzone: "false"
sumologic_collector_default_log_path:
  - { name: "EXAMPLE LOG", path: "/var/log/EXAMPLE.log", use_multiline: false, category: "EXAMPLE" }
```

Group variable example:

```
sumologic_collector_application_log_path:
  - { name: "APP LOG", path: "/var/log/APP.log", use_multiline: false, category: "APP" }
```

Example Playbook
----------------

You can add the role

    - hosts: servers
      roles:
         - role: ansible-sumocollector

License
-------

MIT

Author Information
------------------

William Gregorian, Omada Health, Inc.
