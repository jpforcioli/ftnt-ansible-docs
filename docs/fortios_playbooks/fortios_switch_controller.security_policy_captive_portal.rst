========================================================
fortios_switch_controller.security_policy_captive_portal
========================================================


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
      - name: Names of VLANs that use captive portal authentication.
        fortios_switch_controller.security_policy_captive_portal:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.security_policy_captive_portal:
            state: "present"
            name: "default_name_3"
            policy-type: "captive-portal"
            vlan: "<your_own_value> (source system.interface.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/switch_controller.security_policy/fortios_switch_controller.security_policy_captive_portal_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Names of VLANs that use captive portal authentication.
        fortios_switch_controller.security_policy_captive_portal:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          switch_controller.security_policy_captive_portal:
            state: "present"
            name: "default_name_3"
            policy-type: "captive-portal"
            vlan: "<your_own_value> (source system.interface.name)"




