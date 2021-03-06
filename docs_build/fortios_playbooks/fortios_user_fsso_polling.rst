=========================
fortios_user_fsso_polling
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
      - name: Configure FSSO active directory servers for polling mode.
        fortios_user_fsso_polling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_fsso_polling:
            state: "present"
            adgrp:
             -
                name: "default_name_4"
            default-domain: "<your_own_value>"
            id:  "6"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            logon-history: "8"
            password: "<your_own_value>"
            polling-frequency: "10"
            port: "11"
            server: "192.168.100.40"
            status: "enable"
            user: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_fsso_polling_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure FSSO active directory servers for polling mode.
        fortios_user_fsso_polling:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_fsso_polling:
            state: "present"
            adgrp:
             -
                name: "default_name_4"
            default-domain: "<your_own_value>"
            id:  "6"
            ldap-server: "<your_own_value> (source user.ldap.name)"
            logon-history: "8"
            password: "<your_own_value>"
            polling-frequency: "10"
            port: "11"
            server: "192.168.100.40"
            status: "enable"
            user: "<your_own_value>"




