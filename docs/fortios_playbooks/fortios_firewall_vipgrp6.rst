========================
fortios_firewall_vipgrp6
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
      - name: Configure IPv6 virtual IP groups.
        fortios_firewall_vipgrp6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_vipgrp6:
            state: "present"
            color: "3"
            comments: "<your_own_value>"
            member:
             -
                name: "default_name_6 (source firewall.vip6.name)"
            name: "default_name_7"
            uuid: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

