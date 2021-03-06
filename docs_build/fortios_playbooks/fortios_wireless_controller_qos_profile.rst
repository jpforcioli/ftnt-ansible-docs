=======================================
fortios_wireless_controller_qos_profile
=======================================


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
      - name: Configure WiFi quality of service (QoS) profiles.
        fortios_wireless_controller_qos_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_qos_profile:
            state: "present"
            bandwidth-admission-control: "enable"
            bandwidth-capacity: "4"
            burst: "enable"
            call-admission-control: "enable"
            call-capacity: "7"
            comment: "Comment."
            downlink: "9"
            downlink-sta: "10"
            dscp-wmm-be:
             -
                id:  "12"
            dscp-wmm-bk:
             -
                id:  "14"
            dscp-wmm-mapping: "enable"
            dscp-wmm-vi:
             -
                id:  "17"
            dscp-wmm-vo:
             -
                id:  "19"
            name: "default_name_20"
            uplink: "21"
            uplink-sta: "22"
            wmm: "enable"
            wmm-uapsd: "enable"



Playbook File Examples
----------------------


../ansible_fgt_modules/v6.0.2/wireless_controller/fortios_wireless_controller_qos_profile_example.yml
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. code-block:: yaml
            - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure WiFi quality of service (QoS) profiles.
        fortios_wireless_controller_qos_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          wireless_controller_qos_profile:
            state: "present"
            bandwidth-admission-control: "enable"
            bandwidth-capacity: "4"
            burst: "enable"
            call-admission-control: "enable"
            call-capacity: "7"
            comment: "Comment."
            downlink: "9"
            downlink-sta: "10"
            dscp-wmm-be:
             -
                id:  "12"
            dscp-wmm-bk:
             -
                id:  "14"
            dscp-wmm-mapping: "enable"
            dscp-wmm-vi:
             -
                id:  "17"
            dscp-wmm-vo:
             -
                id:  "19"
            name: "default_name_20"
            uplink: "21"
            uplink-sta: "22"
            wmm: "enable"
            wmm-uapsd: "enable"




