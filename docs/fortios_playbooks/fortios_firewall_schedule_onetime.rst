=================================
fortios_firewall_schedule_onetime
=================================


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
      - name: Onetime schedule configuration.
        fortios_firewall_schedule_onetime:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          firewall_schedule_onetime:
            state: "present"
            color: "3"
            end: "<your_own_value>"
            expiration-days: "5"
            name: "default_name_6"
            start: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

