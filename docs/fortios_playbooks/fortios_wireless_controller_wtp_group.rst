=====================================
fortios_wireless_controller_wtp_group
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
      - name: Configure WTP groups.
        fortios_wireless_controller_wtp_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_wtp_group:
            state: "present"
            name: "default_name_3"
            platform-type: "AP-11N"
            wtps:
             -
                wtp-id: "<your_own_value> (source wireless-controller.wtp.wtp-id)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_wtp_group_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure WTP groups.
        fortios_wireless_controller_wtp_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_wtp_group:
            state: "present"
            name: "default_name_3"
            platform-type: "AP-11N"
            wtps:
             -
                wtp-id: "<your_own_value> (source wireless-controller.wtp.wtp-id)"




