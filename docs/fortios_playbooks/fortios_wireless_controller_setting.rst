===================================
fortios_wireless_controller_setting
===================================


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
      - name: VDOM wireless controller configuration.
        fortios_wireless_controller_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          wireless_controller_setting:
            account-id: "<your_own_value>"
            country: "NA"
            duplicate-ssid: "enable"
            fapc-compatibility: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

