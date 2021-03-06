==================================
fortios_log.fortianalyzer2_setting
==================================


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
      - name: Global FortiAnalyzer settings.
        fortios_log.fortianalyzer2_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.fortianalyzer2_setting:
            __change_ip: "3"
            certificate: "<your_own_value> (source certificate.local.name)"
            conn-timeout: "5"
            enc-algorithm: "high-medium"
            faz-type: "7"
            hmac-algorithm: "sha256"
            ips-archive: "enable"
            mgmt-name: "<your_own_value>"
            monitor-failure-retry-period: "11"
            monitor-keepalive-period: "12"
            reliable: "enable"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            status: "enable"
            upload-day: "<your_own_value>"
            upload-interval: "daily"
            upload-option: "store-and-upload"
            upload-time: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log.fortianalyzer2/fortios_log.fortianalyzer2_setting_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Global FortiAnalyzer settings.
        fortios_log.fortianalyzer2_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.fortianalyzer2_setting:
            __change_ip: "3"
            certificate: "<your_own_value> (source certificate.local.name)"
            conn-timeout: "5"
            enc-algorithm: "high-medium"
            faz-type: "7"
            hmac-algorithm: "sha256"
            ips-archive: "enable"
            mgmt-name: "<your_own_value>"
            monitor-failure-retry-period: "11"
            monitor-keepalive-period: "12"
            reliable: "enable"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            status: "enable"
            upload-day: "<your_own_value>"
            upload-interval: "daily"
            upload-option: "store-and-upload"
            upload-time: "<your_own_value>"




