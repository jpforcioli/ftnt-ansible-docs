===========================
fortios_log.syslogd3_filter
===========================


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
      - name: Filters for remote system server.
        fortios_log.syslogd3_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.syslogd3_filter:
            anomaly: "enable"
            dns: "enable"
            filter: "<your_own_value>"
            filter-type: "include"
            forward-traffic: "enable"
            gtp: "enable"
            local-traffic: "enable"
            multicast-traffic: "enable"
            netscan-discovery: "<your_own_value>"
            netscan-vulnerability: "<your_own_value>"
            severity: "emergency"
            sniffer-traffic: "enable"
            ssh: "enable"
            voip: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/log.syslogd3/fortios_log.syslogd3_filter_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Filters for remote system server.
        fortios_log.syslogd3_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          log.syslogd3_filter:
            anomaly: "enable"
            dns: "enable"
            filter: "<your_own_value>"
            filter-type: "include"
            forward-traffic: "enable"
            gtp: "enable"
            local-traffic: "enable"
            multicast-traffic: "enable"
            netscan-discovery: "<your_own_value>"
            netscan-vulnerability: "<your_own_value>"
            severity: "emergency"
            sniffer-traffic: "enable"
            ssh: "enable"
            voip: "enable"




