========================
fortios_log.disk_setting
========================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Settings for local disk logging.
        fortios_log.disk_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.disk_setting:
            diskfull: "overwrite"
            dlp-archive-quota: "4"
            full-final-warning-threshold: "5"
            full-first-warning-threshold: "6"
            full-second-warning-threshold: "7"
            ips-archive: "enable"
            log-quota: "9"
            max-log-file-size: "10"
            max-policy-packet-capture-size: "11"
            maximum-log-age: "12"
            report-quota: "13"
            roll-day: "sunday"
            roll-schedule: "daily"
            roll-time: "<your_own_value>"
            source-ip: "84.230.14.43"
            status: "enable"
            upload: "enable"
            upload-delete-files: "enable"
            upload-destination: "ftp-server"
            upload-ssl-conn: "default"
            uploaddir: "<your_own_value>"
            uploadip: "<your_own_value>"
            uploadpass: "<your_own_value>"
            uploadport: "26"
            uploadsched: "disable"
            uploadtime: "<your_own_value>"
            uploadtype: "traffic"
            uploaduser: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log.disk/fortios_log.disk_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Settings for local disk logging.
        fortios_log.disk_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.disk_setting:
            diskfull: "overwrite"
            dlp-archive-quota: "4"
            full-final-warning-threshold: "5"
            full-first-warning-threshold: "6"
            full-second-warning-threshold: "7"
            ips-archive: "enable"
            log-quota: "9"
            max-log-file-size: "10"
            max-policy-packet-capture-size: "11"
            maximum-log-age: "12"
            report-quota: "13"
            roll-day: "sunday"
            roll-schedule: "daily"
            roll-time: "<your_own_value>"
            source-ip: "84.230.14.43"
            status: "enable"
            upload: "enable"
            upload-delete-files: "enable"
            upload-destination: "ftp-server"
            upload-ssl-conn: "default"
            uploaddir: "<your_own_value>"
            uploadip: "<your_own_value>"
            uploadpass: "<your_own_value>"
            uploadport: "26"
            uploadsched: "disable"
            uploadtime: "<your_own_value>"
            uploadtype: "traffic"
            uploaduser: "<your_own_value>"




