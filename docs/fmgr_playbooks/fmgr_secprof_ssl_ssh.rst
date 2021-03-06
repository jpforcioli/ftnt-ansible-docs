====================
fmgr_secprof_ssl_ssh
====================


Playbook Task Examples
----------------------

.. code-block:: yaml

      - name: DELETE Profile
        fmgr_secprof_ssl_ssh:
          name: Ansible_SSL_SSH_Profile
          mode: delete
    
      - name: CREATE Profile
        fmgr_secprof_ssl_ssh:
          name: Ansible_SSL_SSH_Profile
          comment: "Created by Ansible Module TEST"
          mode: set
          mapi_over_https: enable
          rpc_over_https: enable
          server_cert_mode: replace
          ssl_anomalies_log: enable
          ssl_exemptions_log: enable
          use_ssl_server: enable
          whitelist: enable



Playbook File Examples
----------------------


ssl.yml
+++++++

.. code-block:: yaml



    - name: Create and Delete security profile in FMG
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: DELETE Profile
        fmgr_secprof_ssl_ssh:
          name: "Ansible_SSL_SSH_Profile"
          mode: "delete"
    
      - name: CREATE Profile
        fmgr_secprof_ssl_ssh:
          name: "Ansible_SSL_SSH_Profile"
          comment: "Created by Ansible Module TEST"
          mode: "set"
          mapi_over_https: "enable"
          rpc_over_https: "enable"
          server_cert_mode: "replace"
          ssl_anomalies_log: "enable"
          ssl_exemptions_log: "enable"
          use_ssl_server: "enable"
          whitelist: "enable"
    
    


fmgr_secprof_ssl_ssh_run_all.sh
+++++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook ssl.yml -vvvv




