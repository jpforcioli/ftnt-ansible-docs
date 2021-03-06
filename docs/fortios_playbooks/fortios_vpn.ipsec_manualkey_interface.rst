=====================================
fortios_vpn.ipsec_manualkey_interface
=====================================


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
      - name: Configure IPsec manual keys.
        fortios_vpn.ipsec_manualkey_interface:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_manualkey_interface:
            state: "present"
            addr-type: "4"
            auth-alg: "null"
            auth-key: "<your_own_value>"
            enc-alg: "null"
            enc-key: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            ip-version: "4"
            local-gw: "<your_own_value>"
            local-gw6: "<your_own_value>"
            local-spi: "<your_own_value>"
            name: "default_name_13"
            npu-offload: "enable"
            remote-gw: "<your_own_value>"
            remote-gw6: "<your_own_value>"
            remote-spi: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/vpn.ipsec/fortios_vpn.ipsec_manualkey_interface_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure IPsec manual keys.
        fortios_vpn.ipsec_manualkey_interface:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          vpn.ipsec_manualkey_interface:
            state: "present"
            addr-type: "4"
            auth-alg: "null"
            auth-key: "<your_own_value>"
            enc-alg: "null"
            enc-key: "<your_own_value>"
            interface: "<your_own_value> (source system.interface.name)"
            ip-version: "4"
            local-gw: "<your_own_value>"
            local-gw6: "<your_own_value>"
            local-spi: "<your_own_value>"
            name: "default_name_13"
            npu-offload: "enable"
            remote-gw: "<your_own_value>"
            remote-gw6: "<your_own_value>"
            remote-spi: "<your_own_value>"




