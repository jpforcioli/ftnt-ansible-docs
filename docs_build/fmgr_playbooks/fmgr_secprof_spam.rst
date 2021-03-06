=================
fmgr_secprof_spam
=================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_spam:
          name: "Ansible_Spam_Filter_Profile"
          mode: "delete"
    
      - name: Create FMGR_SPAMFILTER_PROFILE
        fmgr_secprof_spam:
          host: "{{ inventory_hostname }}"
          username: "{{ username }}"
          password: "{{ password }}"
          mode: "set"
          adom: "root"
          spam_log_fortiguard_response: "enable"
          spam_iptrust_table:
          spam_filtering: "enable"
          spam_bword_threshold: 10
          options: ["bannedword", "spamfsip", "spamfsurl", "spamrbl", "spamfsphish", "spambwl"]
          name: "Ansible_Spam_Filter_Profile"
          flow_based: "enable"
          external: "enable"
          comment: "Created by Ansible"
          gmail_log: "enable"
          spam_log: "enable"



Playbook File Examples
----------------------


fmgr_secprof_spam_run_all.sh
++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook spam.yml -vvvv


spam.yml
++++++++

.. code-block:: yaml



    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_spam:
          name: "Ansible_Spam_Filter_Profile"
          mode: "delete"
    
      - name: Create FMGR_SPAMFILTER_PROFILE
        fmgr_secprof_spam:
          mode: "set"
          adom: "root"
          spam_log_fortiguard_response: "enable"
          spam_iptrust_table:
          spam_filtering: "enable"
          spam_bword_threshold: 10
          options: ["bannedword", "spamfsip", "spamfsurl", "spamrbl", "spamfsphish", "spambwl"]
          name: "Ansible_Spam_Filter_Profile"
          flow_based: "enable"
          external: "enable"
          comment: "Created by Ansible"
          gmail_log: "enable"
          spam_log: "enable"



