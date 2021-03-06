============================
fortios_system_vdom_property
============================


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
      - name: Configure VDOM property.
        fortios_system_vdom_property:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_property:
            state: "present"
            custom-service: "<your_own_value>"
            description: "<your_own_value>"
            dialup-tunnel: "<your_own_value>"
            firewall-address: "<your_own_value>"
            firewall-addrgrp: "<your_own_value>"
            firewall-policy: "<your_own_value>"
            ipsec-phase1: "<your_own_value>"
            ipsec-phase1-interface: "<your_own_value>"
            ipsec-phase2: "<your_own_value>"
            ipsec-phase2-interface: "<your_own_value>"
            log-disk-quota: "<your_own_value>"
            name: "default_name_14 (source system.vdom.name)"
            onetime-schedule: "<your_own_value>"
            proxy: "<your_own_value>"
            recurring-schedule: "<your_own_value>"
            service-group: "<your_own_value>"
            session: "<your_own_value>"
            snmp-index: "20"
            sslvpn: "<your_own_value>"
            user: "<your_own_value>"
            user-group: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_property_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure VDOM property.
        fortios_system_vdom_property:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_property:
            state: "present"
            custom-service: "<your_own_value>"
            description: "<your_own_value>"
            dialup-tunnel: "<your_own_value>"
            firewall-address: "<your_own_value>"
            firewall-addrgrp: "<your_own_value>"
            firewall-policy: "<your_own_value>"
            ipsec-phase1: "<your_own_value>"
            ipsec-phase1-interface: "<your_own_value>"
            ipsec-phase2: "<your_own_value>"
            ipsec-phase2-interface: "<your_own_value>"
            log-disk-quota: "<your_own_value>"
            name: "default_name_14 (source system.vdom.name)"
            onetime-schedule: "<your_own_value>"
            proxy: "<your_own_value>"
            recurring-schedule: "<your_own_value>"
            service-group: "<your_own_value>"
            session: "<your_own_value>"
            snmp-index: "20"
            sslvpn: "<your_own_value>"
            user: "<your_own_value>"
            user-group: "<your_own_value>"




