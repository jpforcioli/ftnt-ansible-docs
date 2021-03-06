=========================
fortios_certificate_local
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
      - name: Local keys and certificates.
        fortios_certificate_local:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          certificate_local:
            state: "present"
            auto-regenerate-days: "3"
            auto-regenerate-days-warning: "4"
            ca-identifier:  "myId_5"
            certificate: "<your_own_value>"
            cmp-path: "<your_own_value>"
            cmp-regeneration-method: "keyupate"
            cmp-server: "<your_own_value>"
            cmp-server-cert: "<your_own_value> (source certificate.ca.name)"
            comments: "<your_own_value>"
            csr: "<your_own_value>"
            enroll-protocol: "none"
            ike-localid: "<your_own_value>"
            ike-localid-type: "asn1dn"
            last-updated: "16"
            name: "default_name_17"
            name-encoding: "printable"
            password: "<your_own_value>"
            private-key: "<your_own_value>"
            range: "global"
            scep-password: "<your_own_value>"
            scep-url: "<your_own_value>"
            source: "factory"
            source-ip: "84.230.14.43"
            state: "<your_own_value>"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/certificate/fortios_certificate_local_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Local keys and certificates.
        fortios_certificate_local:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          certificate_local:
            state: "present"
            auto-regenerate-days: "3"
            auto-regenerate-days-warning: "4"
            ca-identifier:  "myId_5"
            certificate: "<your_own_value>"
            cmp-path: "<your_own_value>"
            cmp-regeneration-method: "keyupate"
            cmp-server: "<your_own_value>"
            cmp-server-cert: "<your_own_value> (source certificate.ca.name)"
            comments: "<your_own_value>"
            csr: "<your_own_value>"
            enroll-protocol: "none"
            ike-localid: "<your_own_value>"
            ike-localid-type: "asn1dn"
            last-updated: "16"
            name: "default_name_17"
            name-encoding: "printable"
            password: "<your_own_value>"
            private-key: "<your_own_value>"
            range: "global"
            scep-password: "<your_own_value>"
            scep-url: "<your_own_value>"
            source: "factory"
            source-ip: "84.230.14.43"
            state: "<your_own_value>"




