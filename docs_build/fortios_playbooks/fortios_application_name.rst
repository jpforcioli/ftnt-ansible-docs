========================
fortios_application_name
========================


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
      - name: Configure application signatures.
        fortios_application_name:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          application_name:
            state: "present"
            behavior: "<your_own_value>"
            category: "4"
            id:  "5"
            metadata:
             -
                id:  "7"
                metaid: "8"
                valueid: "9"
            name: "default_name_10"
            parameter: "<your_own_value>"
            popularity: "12"
            protocol: "<your_own_value>"
            risk: "14"
            sub-category: "15"
            technology: "<your_own_value>"
            vendor: "<your_own_value>"
            weight: "18"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

