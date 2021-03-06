================================
fortios_firewall_ssl_ssh_profile
================================


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
      - name: Configure SSL/SSH protocol options.
        fortios_firewall_ssl_ssh_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          firewall_ssl_ssh_profile:
            state: "present"
            caname: "<your_own_value> (source vpn.certificate.local.name)"
            comment: "Optional comments."
            ftps:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                ports: "8"
                status: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            https:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                ports: "15"
                status: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            imaps:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                ports: "22"
                status: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            mapi-over-https: "enable"
            name: "default_name_27"
            pop3s:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                ports: "31"
                status: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            rpc-over-https: "enable"
            server-cert: "<your_own_value> (source vpn.certificate.local.name)"
            server-cert-mode: "re-sign"
            smtps:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                ports: "41"
                status: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            ssh:
                inspect-all: "disable"
                ports: "47"
                ssh-algorithm: "compatible"
                ssh-policy-check: "disable"
                ssh-tun-policy-check: "disable"
                status: "disable"
                unsupported-version: "bypass"
            ssl:
                allow-invalid-server-cert: "enable"
                client-cert-request: "bypass"
                inspect-all: "disable"
                unsupported-ssl: "bypass"
                untrusted-cert: "allow"
            ssl-anomalies-log: "disable"
            ssl-exempt:
             -
                address: "<your_own_value> (source firewall.address.name firewall.addrgrp.name)"
                address6: "<your_own_value> (source firewall.address6.name firewall.addrgrp6.name)"
                fortiguard-category: "63"
                id:  "64"
                regex: "<your_own_value>"
                type: "fortiguard-category"
                wildcard-fqdn: "<your_own_value> (source firewall.wildcard-fqdn.custom.name firewall.wildcard-fqdn.group.name)"
            ssl-exemptions-log: "disable"
            ssl-server:
             -
                ftps-client-cert-request: "bypass"
                https-client-cert-request: "bypass"
                id:  "72"
                imaps-client-cert-request: "bypass"
                ip: "<your_own_value>"
                pop3s-client-cert-request: "bypass"
                smtps-client-cert-request: "bypass"
                ssl-other-client-cert-request: "bypass"
            untrusted-caname: "<your_own_value> (source vpn.certificate.local.name)"
            use-ssl-server: "disable"
            whitelist: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

