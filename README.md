Role Name
=========

Ansible role to install SumoCollector. This role was inspired by William Gregorian's SumoCollector.
I added support for installing on centos.
I am also respecting the source use_multiline setting

Role Variables
--------------

Default variables:

```
sumocollector_installer_rpm: https://collectors.sumologic.com/rest/download/rpm/64
sumologic_installer_rpm_local_folder: /tmp
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
Forked from: William Gregorian, Omada Health, Inc. 


Open to pull requests.
