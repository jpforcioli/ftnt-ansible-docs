===============================
fortios_endpoint_control_client
===============================


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
      - name: Configure endpoint control client lists.
        fortios_endpoint_control_client:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          endpoint_control_client:
            state: "present"
            ad-groups: "<your_own_value>"
            ftcl-uid: "<your_own_value>"
            id:  "5"
            info: "<your_own_value>"
            src-ip: "<your_own_value>"
            src-mac: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

