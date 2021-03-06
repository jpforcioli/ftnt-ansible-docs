=================
fortios_user_ldap
=================


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
      - name: Configure LDAP server entries.
        fortios_user_ldap:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_ldap:
            state: "present"
            account-key-filter: "<your_own_value>"
            account-key-processing: "same"
            ca-cert: "<your_own_value> (source vpn.certificate.ca.name)"
            cnid: "<your_own_value>"
            dn: "<your_own_value>"
            group-filter: "<your_own_value>"
            group-member-check: "user-attr"
            group-object-filter: "<your_own_value>"
            group-search-base: "<your_own_value>"
            member-attr: "<your_own_value>"
            name: "default_name_13"
            password: "<your_own_value>"
            password-expiry-warning: "enable"
            password-renewal: "enable"
            port: "17"
            secondary-server: "<your_own_value>"
            secure: "disable"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            tertiary-server: "<your_own_value>"
            type: "simple"
            username: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/user/fortios_user_ldap_example.yml
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure LDAP server entries.
        fortios_user_ldap:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          user_ldap:
            state: "present"
            account-key-filter: "<your_own_value>"
            account-key-processing: "same"
            ca-cert: "<your_own_value> (source vpn.certificate.ca.name)"
            cnid: "<your_own_value>"
            dn: "<your_own_value>"
            group-filter: "<your_own_value>"
            group-member-check: "user-attr"
            group-object-filter: "<your_own_value>"
            group-search-base: "<your_own_value>"
            member-attr: "<your_own_value>"
            name: "default_name_13"
            password: "<your_own_value>"
            password-expiry-warning: "enable"
            password-renewal: "enable"
            port: "17"
            secondary-server: "<your_own_value>"
            secure: "disable"
            server: "192.168.100.40"
            source-ip: "84.230.14.43"
            ssl-min-proto-version: "default"
            tertiary-server: "<your_own_value>"
            type: "simple"
            username: "<your_own_value>"




