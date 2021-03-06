=============================
fortios_system_object_tagging
=============================


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
      - name: Configure object tagging.
        fortios_system_object_tagging:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_object_tagging:
            state: "present"
            address: "disable"
            category: "<your_own_value>"
            color: "5"
            device: "disable"
            interface: "disable"
            multiple: "enable"
            tags:
             -
                name: "default_name_10"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_object_tagging_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure object tagging.
        fortios_system_object_tagging:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_object_tagging:
            state: "present"
            address: "disable"
            category: "<your_own_value>"
            color: "5"
            device: "disable"
            interface: "disable"
            multiple: "enable"
            tags:
             -
                name: "default_name_10"




