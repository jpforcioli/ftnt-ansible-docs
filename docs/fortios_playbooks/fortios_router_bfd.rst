==================
fortios_router_bfd
==================


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
      - name: Configure BFD.
        fortios_router_bfd:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          router_bfd:
            neighbor:
             -
                interface: "<your_own_value> (source system.interface.name)"
                ip: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

