===============================
fortios_firewall_dnstranslation
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
      - name: Configure DNS translation.
        fortios_firewall_dnstranslation:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall_dnstranslation:
            state: "present"
            dst: "<your_own_value>"
            id:  "4"
            netmask: "<your_own_value>"
            src: "<your_own_value>"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

