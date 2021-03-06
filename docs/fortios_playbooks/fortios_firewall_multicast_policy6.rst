==================================
fortios_firewall_multicast_policy6
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
      - name: Configure IPv6 multicast NAT policies.
        fortios_firewall_multicast_policy6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          firewall_multicast_policy6:
            state: "present"
            action: "accept"
            dstaddr:
             -
                name: "default_name_5 (source firewall.multicast-address6.name)"
            dstintf: "<your_own_value> (source system.interface.name system.zone.name)"
            end-port: "7"
            id:  "8"
            logtraffic: "enable"
            protocol: "10"
            srcaddr:
             -
                name: "default_name_12 (source firewall.address6.name firewall.addrgrp6.name)"
            srcintf: "<your_own_value> (source system.interface.name system.zone.name)"
            start-port: "14"
            status: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

