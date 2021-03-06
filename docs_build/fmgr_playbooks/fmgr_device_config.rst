==================
fmgr_device_config
==================


Playbook Task Examples
----------------------

.. code-block:: yaml

    - name: CHANGE HOSTNAME
      fmgr_device_config:
        device_hostname: "ChangedbyAnsible"
        device_unique_name: "FGT1"
    
    - name: EDIT INTERFACE INFORMATION
      fmgr_device_config:
        adom: "root"
        device_unique_name: "FGT2"
        interface: "port3"
        interface_ip: "10.1.1.1/24"
        interface_allow_access: "ping, telnet, https"
    
    - name: INSTALL CONFIG
      fmgr_device_config:
        adom: "root"
        device_unique_name: "FGT1"
        install_config: "enable"



Playbook File Examples
----------------------


fmgr_device_exec_config.yml
+++++++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: INSTALL CONFIG FGT1
          fmgr_device_config:
            adom: "ansible"
            device_unique_name: "FGT1"
            install_config: "enable"
    
        - name: INSTALL CONFIG FGT2 and FGT3
          fmgr_device_config:
            adom: "ansible"
            device_unique_name: "FGT2, FGT3"
            install_config: "enable"


fmgr_device_config_run_all.sh
+++++++++++++++++++++++++++++

.. code-block:: shell

            #!/bin/bash
    ansible-playbook fmgr_device_exec_config.yml -vvvv
    ansible-playbook fgt01_config.yml -vvvv
    ansible-playbook fgt03_config.yml -vvvv
    ansible-playbook fmgr_device_config.yml -vvvv
    ansible-playbook fgt02_config.yml -vvvv


fgt01_config.yml
++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FGT HOSTNAME AND INTERFACE
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: CHANGE HOSTNAME
        fmgr_device_config:
          device_hostname: "ansible-fgt01"
          device_unique_name: "FGT1"
          adom: "ansible"
    
    
      - name: EDIT INTERFACE INFORMATION
        fmgr_device_config:
          adom: "ansible"
          device_unique_name: "FGT1"
          interface: "port2"
          interface_ip: "10.1.1.1/24"
          interface_allow_access: "ping, telnet, https, http"


fgt03_config.yml
++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FGT HOSTNAME AND INTERFACE
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: CHANGE HOSTNAME
        fmgr_device_config:
          #the new hostname for the Fortigate
          device_hostname: "ansible-fgt03"
          #the "friendly name" of the device in FortiManager
          device_unique_name: "FGT3"
          #adom to put the device in
          adom: "ansible"
    
    
      - name: EDIT INTERFACE INFORMATION
        fmgr_device_config:
          adom: "ansible"
          device_unique_name: "FGT3"
          #interface to configure
          interface: "port2"
          #ip address to add to interface
          interface_ip: "10.1.3.1/24"
          #edit management access
          interface_allow_access: "ping, telnet, https, http"


fmgr_device_config.yml
++++++++++++++++++++++

.. code-block:: yaml



    - name: DISCOVER AND ADD DEVICES
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
        - name: CHANGE HOSTNAME
          fmgr_device_config:
            device_hostname: "ChangedbyAnsible"
            device_unique_name: "FGT1"
    
        - name: EDIT INTERFACE INFORMATION
          fmgr_device_config:
            adom: "root"
            device_unique_name: "FGT2"
            interface: "port3"
            interface_ip: "10.255.1.1/24"
            interface_allow_access: "ping, telnet, https, http"


fgt02_config.yml
++++++++++++++++

.. code-block:: yaml



    
    - name: CONFIG FGT HOSTNAME AND INTERFACE
      hosts: FortiManager
      connection: httpapi
      gather_facts: False
    
      tasks:
    
      - name: CHANGE HOSTNAME
        fmgr_device_config:
          #hard coded fortimanager example host and login -- see "fmg_group_add.yml for ansible host file version"
          #the new hostname for the fortigate
          device_hostname: "ansible-fgt02"
          #the "friendly name" of the device in FortiManager
          device_unique_name: "FGT2"
          #adom for device
          adom: "ansible"
    
    
      - name: EDIT INTERFACE INFORMATION
        fmgr_device_config:
          adom: "ansible"
          device_unique_name: "FGT2"
          #interface to configure
          interface: "port2"
          #ip address to add to interface
          interface_ip: "10.1.2.1/24"
          #edit management access
          interface_allow_access: "ping, telnet, https, http"




