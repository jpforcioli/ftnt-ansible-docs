==========================
fortios_spamfilter_profile
==========================


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
      - name: Configure AntiSpam profiles.
        fortios_spamfilter_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          spamfilter_profile:
            state: "present"
            comment: "Comment."
            external: "enable"
            flow-based: "enable"
            gmail:
                log: "enable"
            imap:
                action: "pass"
                log: "enable"
                tag-msg: "<your_own_value>"
                tag-type: "subject"
            mapi:
                action: "pass"
                log: "enable"
            msn-hotmail:
                log: "enable"
            name: "default_name_18"
            options: "bannedword"
            pop3:
                action: "pass"
                log: "enable"
                tag-msg: "<your_own_value>"
                tag-type: "subject"
            replacemsg-group: "<your_own_value> (source system.replacemsg-group.name)"
            smtp:
                action: "pass"
                hdrip: "disable"
                local-override: "disable"
                log: "enable"
                tag-msg: "<your_own_value>"
                tag-type: "subject"
            spam-bwl-table: "33 (source spamfilter.bwl.id)"
            spam-bword-table: "34 (source spamfilter.bword.id)"
            spam-bword-threshold: "35"
            spam-filtering: "enable"
            spam-iptrust-table: "37 (source spamfilter.iptrust.id)"
            spam-log: "disable"
            spam-log-fortiguard-response: "disable"
            spam-mheader-table: "40 (source spamfilter.mheader.id)"
            spam-rbl-table: "41 (source spamfilter.dnsbl.id)"
            yahoo-mail:
                log: "enable"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

