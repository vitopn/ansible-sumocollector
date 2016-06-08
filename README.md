Role Name
=========

Ansible role to install SumoCollector. This role was inspired by William Gregorian's SumoCollector.
I added support for installing on centos.
I am also respecting the source use_multiline setting

Role Variables
--------------

Default variables:


Always apply:
```
sumologic_collector_accessid: ""
sumologic_collector_accesskey: ""
sumologic_installer_file: ""
sumologic_collector_source_template: "collector.json.j2"
sumologic_local_file_configuration_management: false
sumologic_collector_timezone: "UTC"
sumologic_collector_force_timzone: "false"
sumologic_collector_default_log_path:
  - { name: "Sys Log", path: "/var/log/syslog.log", use_multiline: false, category: "OS/Linux/Syslog" }
```

Debian:
```
sumocollector_installer_deb: "https://collectors.sumologic.com/rest/download/deb/64"
sumologic_installer_deb_local_file: /tmp/sumocollector.deb

```

RedHat:
```
sumocollector_installer_rpm: https://collectors.sumologic.com/rest/download/rpm/64
sumologic_installer_rpm_local_folder: /tmp

```


Group variable example:

```
sumologic_collector_application_log_path:
  - { name: "APP LOG", path: "/var/log/APP.log", use_multiline: false, category: "APP" }
```

Example with multiline processing (Infer Boundaries)
```
sumologic_collector_application_log_path:
  - { name: "Tomcat", path: "/usr/local/tomcat/logs/catalina.out", use_multiline: true, category: "staging/tomcat/catalina" }
```

Example with Boundary Regex for manual multiline processing.
```
sumologic_collector_application_log_path:
  - { name: "Tomcat", path: "/usr/local/tomcat/logs/catalina.out", use_multiline: true, category: "staging/tomcat/catalina", use_autoline_matching: false, manual_prefix_regex: 'Timestamp=[\\d-:]+ [\\d:,]+\\s\\|\\sPriority=\\w+\\s+\\|\\sCategory=\\S+\\s\\|\\sLine=\\d+\\s\\|\\sThread=[\\w\\d-]+\\s\\|\\sMessage=.*' }
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
