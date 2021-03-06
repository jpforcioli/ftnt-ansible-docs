============================
fortios_firewall.ssl_setting
============================


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
      - name: SSL proxy settings.
        fortios_firewall.ssl_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          firewall.ssl_setting:
            abbreviate-handshake: "enable"
            cert-cache-capacity: "4"
            cert-cache-timeout: "5"
            kxp-queue-threshold: "6"
            no-matching-cipher-action: "bypass"
            proxy-connect-timeout: "8"
            session-cache-capacity: "9"
            session-cache-timeout: "10"
            ssl-dh-bits: "768"
            ssl-queue-threshold: "12"
            ssl-send-empty-frags: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

