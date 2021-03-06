=============================
fortios_system_vdom_exception
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
      - name: Global configuration objects that can be configured independently for all VDOMs or for the defined VDOM scope.
        fortios_system_vdom_exception:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_exception:
            state: "present"
            id:  "3"
            object: "log.fortianalyzer.setting"
            oid: "5"
            scope: "all"
            vdom:
             -
                name: "default_name_8 (source system.vdom.name)"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/system/fortios_system_vdom_exception_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Global configuration objects that can be configured independently for all VDOMs or for the defined VDOM scope.
        fortios_system_vdom_exception:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_vdom_exception:
            state: "present"
            id:  "3"
            object: "log.fortianalyzer.setting"
            oid: "5"
            scope: "all"
            vdom:
             -
                name: "default_name_8 (source system.vdom.name)"




