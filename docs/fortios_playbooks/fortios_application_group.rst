=========================
fortios_application_group
=========================


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
      - name: Configure firewall application groups.
        fortios_application_group:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          application_group:
            state: "present"
            application:
             -
                id:  "4"
            category:
             -
                id:  "6"
            comment: "Comment"
            name: "default_name_8"
            type: "application"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

