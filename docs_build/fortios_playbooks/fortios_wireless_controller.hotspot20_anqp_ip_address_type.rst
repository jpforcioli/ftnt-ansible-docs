==========================================================
fortios_wireless_controller.hotspot20_anqp_ip_address_type
==========================================================


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
      - name: Configure IP address type availability.
        fortios_wireless_controller.hotspot20_anqp_ip_address_type:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller.hotspot20_anqp_ip_address_type:
            state: "present"
            ipv4-address-type: "not-available"
            ipv6-address-type: "not-available"
            name: "default_name_5"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

