==================
fortios_system_ntp
==================


Metadata
--------




**Name:** fortios_system_ntp

**Description:** This module is able to configure a FortiGate or FortiOS by allowing the user to configure system feature and ntp category. Examples includes all options and need to be adjusted to datasources before usage. Tested with FOS v6.0.2


**Author(s):** 

- Miguel Angel Munoz (github: @mamunozgonzalez)

- Nicolas Thomas (github: @thomnico)



**Ansible Version Added/Required:** 2.8

**Dev Status:** No Data Exists. Contact DevOps Team.

Parameters
----------

host
++++

- Description: FortiOS or FortiGate ip adress.

  

- Required: True

https
+++++

- Description: Indicates if the requests towards FortiGate must use HTTPS protocol

  

- default: False

password
++++++++

- Description: FortiOS or FortiGate password.

  

- default: 

system_ntp
++++++++++

- Description: Configure system NTP information.

  

- default: None

username
++++++++

- Description: FortiOS or FortiGate username.

  

- Required: True

vdom
++++

- Description: Virtual domain, among those defined previously. A vdom is a virtual instance of the FortiGate that can be configured and used as a different unit.

  

- default: root




Functions
---------




- login

 .. code-block:: python

    def login(data):
        host = data['host']
        username = data['username']
        password = data['password']
    
        fos.debug('on')
        if 'https' in data and not data['https']:
            fos.https('off')
        else:
            fos.https('on')
    
        fos.login(host, username, password)
    
    

- filter_system_ntp_data

 .. code-block:: python

    def filter_system_ntp_data(json):
        option_list = ['interface', 'ntpserver', 'ntpsync',
                       'server-mode', 'source-ip', 'syncinterval',
                       'type']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    

- system_ntp

 .. code-block:: python

    def system_ntp(data, fos):
        vdom = data['vdom']
        system_ntp_data = data['system_ntp']
        filtered_data = filter_system_ntp_data(system_ntp_data)
        return fos.set('system',
                       'ntp',
                       data=filtered_data,
                       vdom=vdom)
    
    

- fortios_system

 .. code-block:: python

    def fortios_system(data, fos):
        login(data)
    
        methodlist = ['system_ntp']
        for method in methodlist:
            if data[method]:
                resp = eval(method)(data, fos)
                break
    
        fos.logout()
        return not resp['status'] == "success", resp['status'] == "success", resp
    
    

- main

 .. code-block:: python

    def main():
        fields = {
            "host": {"required": True, "type": "str"},
            "username": {"required": True, "type": "str"},
            "password": {"required": False, "type": "str", "no_log": True},
            "vdom": {"required": False, "type": "str", "default": "root"},
            "https": {"required": False, "type": "bool", "default": "False"},
            "system_ntp": {
                "required": False, "type": "dict",
                "options": {
                    "interface": {"required": False, "type": "list",
                                  "options": {
                                      "interface-name": {"required": True, "type": "str"}
                                  }},
                    "ntpserver": {"required": False, "type": "list",
                                  "options": {
                                      "authentication": {"required": False, "type": "str",
                                                         "choices": ["enable", "disable"]},
                                      "id": {"required": True, "type": "int"},
                                      "key": {"required": False, "type": "str"},
                                      "key-id": {"required": False, "type": "int"},
                                      "ntpv3": {"required": False, "type": "str",
                                                "choices": ["enable", "disable"]},
                                      "server": {"required": False, "type": "str"}
                                  }},
                    "ntpsync": {"required": False, "type": "str",
                                "choices": ["enable", "disable"]},
                    "server-mode": {"required": False, "type": "str",
                                    "choices": ["enable", "disable"]},
                    "source-ip": {"required": False, "type": "str"},
                    "syncinterval": {"required": False, "type": "int"},
                    "type": {"required": False, "type": "str",
                             "choices": ["fortiguard", "custom"]}
    
                }
            }
        }
    
        module = AnsibleModule(argument_spec=fields,
                               supports_check_mode=False)
        try:
            from fortiosapi import FortiOSAPI
        except ImportError:
            module.fail_json(msg="fortiosapi module is required")
    
        global fos
        fos = FortiOSAPI()
    
        is_error, has_changed, result = fortios_system(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    



Module Source Code
------------------

.. code-block:: python

    #!/usr/bin/python
    from __future__ import (absolute_import, division, print_function)
    # Copyright 2018 Fortinet, Inc.
    #
    # This program is free software: you can redistribute it and/or modify
    # it under the terms of the GNU General Public License as published by
    # the Free Software Foundation, either version 3 of the License, or
    # (at your option) any later version.
    #
    # This program is distributed in the hope that it will be useful,
    # but WITHOUT ANY WARRANTY; without even the implied warranty of
    # MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    # GNU General Public License for more details.
    #
    # You should have received a copy of the GNU General Public License
    # along with this program.  If not, see <https://www.gnu.org/licenses/>.
    #
    # the lib use python logging can get it if the following is set in your
    # Ansible config.
    
    __metaclass__ = type
    
    ANSIBLE_METADATA = {'status': ['preview'],
                        'supported_by': 'community',
                        'metadata_version': '1.1'}
    
    DOCUMENTATION = '''
    ---
    module: fortios_system_ntp
    short_description: Configure system NTP information.
    description:
        - This module is able to configure a FortiGate or FortiOS by
          allowing the user to configure system feature and ntp category.
          Examples includes all options and need to be adjusted to datasources before usage.
          Tested with FOS v6.0.2
    version_added: "2.8"
    author:
        - Miguel Angel Munoz (@mamunozgonzalez)
        - Nicolas Thomas (@thomnico)
    notes:
        - Requires fortiosapi library developed by Fortinet
        - Run as a local_action in your playbook
    requirements:
        - fortiosapi>=0.9.8
    options:
        host:
           description:
                - FortiOS or FortiGate ip adress.
           required: true
        username:
            description:
                - FortiOS or FortiGate username.
            required: true
        password:
            description:
                - FortiOS or FortiGate password.
            default: ""
        vdom:
            description:
                - Virtual domain, among those defined previously. A vdom is a
                  virtual instance of the FortiGate that can be configured and
                  used as a different unit.
            default: root
        https:
            description:
                - Indicates if the requests towards FortiGate must use HTTPS
                  protocol
            type: bool
            default: false
        system_ntp:
            description:
                - Configure system NTP information.
            default: null
            suboptions:
                interface:
                    description:
                        - FortiGate interface(s) with NTP server mode enabled. Devices on your network can contact these interfaces for NTP services.
                    suboptions:
                        interface-name:
                            description:
                                - Interface name. Source system.interface.name.
                            required: true
                ntpserver:
                    description:
                        - Configure the FortiGate to connect to any available third-party NTP server.
                    suboptions:
                        authentication:
                            description:
                                - Enable/disable MD5 authentication.
                            choices:
                                - enable
                                - disable
                        id:
                            description:
                                - NTP server ID.
                            required: true
                        key:
                            description:
                                - Key for MD5 authentication.
                        key-id:
                            description:
                                - Key ID for authentication.
                        ntpv3:
                            description:
                                - Enable to use NTPv3 instead of NTPv4.
                            choices:
                                - enable
                                - disable
                        server:
                            description:
                                - IP address or hostname of the NTP Server.
                ntpsync:
                    description:
                        - Enable/disable setting the FortiGate system time by synchronizing with an NTP Server.
                    choices:
                        - enable
                        - disable
                server-mode:
                    description:
                        - Enable/disable FortiGate NTP Server Mode. Your FortiGate becomes an NTP server for other devices on your network. The FortiGate relays
                           NTP requests to its configured NTP server.
                    choices:
                        - enable
                        - disable
                source-ip:
                    description:
                        - Source IP for communications to the NTP server.
                syncinterval:
                    description:
                        - NTP synchronization interval (1 - 1440 min).
                type:
                    description:
                        - Use the FortiGuard NTP server or any other available NTP Server.
                    choices:
                        - fortiguard
                        - custom
    '''
    
    EXAMPLES = '''
    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Configure system NTP information.
        fortios_system_ntp:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          system_ntp:
            interface:
             -
                interface-name: "<your_own_value> (source system.interface.name)"
            ntpserver:
             -
                authentication: "enable"
                id:  "7"
                key: "<your_own_value>"
                key-id: "9"
                ntpv3: "enable"
                server: "192.168.100.40"
            ntpsync: "enable"
            server-mode: "enable"
            source-ip: "84.230.14.43"
            syncinterval: "15"
            type: "fortiguard"
    '''
    
    RETURN = '''
    build:
      description: Build number of the fortigate image
      returned: always
      type: string
      sample: '1547'
    http_method:
      description: Last method used to provision the content into FortiGate
      returned: always
      type: string
      sample: 'PUT'
    http_status:
      description: Last result given by FortiGate on last operation applied
      returned: always
      type: string
      sample: "200"
    mkey:
      description: Master key (id) used in the last call to FortiGate
      returned: success
      type: string
      sample: "key1"
    name:
      description: Name of the table used to fulfill the request
      returned: always
      type: string
      sample: "urlfilter"
    path:
      description: Path of the table used to fulfill the request
      returned: always
      type: string
      sample: "webfilter"
    revision:
      description: Internal revision number
      returned: always
      type: string
      sample: "17.0.2.10658"
    serial:
      description: Serial number of the unit
      returned: always
      type: string
      sample: "FGVMEVYYQT3AB5352"
    status:
      description: Indication of the operation's result
      returned: always
      type: string
      sample: "success"
    vdom:
      description: Virtual domain used
      returned: always
      type: string
      sample: "root"
    version:
      description: Version of the FortiGate
      returned: always
      type: string
      sample: "v5.6.3"
    
    '''
    
    from ansible.module_utils.basic import AnsibleModule
    
    fos = None
    
    
    def login(data):
        host = data['host']
        username = data['username']
        password = data['password']
    
        fos.debug('on')
        if 'https' in data and not data['https']:
            fos.https('off')
        else:
            fos.https('on')
    
        fos.login(host, username, password)
    
    
    def filter_system_ntp_data(json):
        option_list = ['interface', 'ntpserver', 'ntpsync',
                       'server-mode', 'source-ip', 'syncinterval',
                       'type']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    
    def system_ntp(data, fos):
        vdom = data['vdom']
        system_ntp_data = data['system_ntp']
        filtered_data = filter_system_ntp_data(system_ntp_data)
        return fos.set('system',
                       'ntp',
                       data=filtered_data,
                       vdom=vdom)
    
    
    def fortios_system(data, fos):
        login(data)
    
        methodlist = ['system_ntp']
        for method in methodlist:
            if data[method]:
                resp = eval(method)(data, fos)
                break
    
        fos.logout()
        return not resp['status'] == "success", resp['status'] == "success", resp
    
    
    def main():
        fields = {
            "host": {"required": True, "type": "str"},
            "username": {"required": True, "type": "str"},
            "password": {"required": False, "type": "str", "no_log": True},
            "vdom": {"required": False, "type": "str", "default": "root"},
            "https": {"required": False, "type": "bool", "default": "False"},
            "system_ntp": {
                "required": False, "type": "dict",
                "options": {
                    "interface": {"required": False, "type": "list",
                                  "options": {
                                      "interface-name": {"required": True, "type": "str"}
                                  }},
                    "ntpserver": {"required": False, "type": "list",
                                  "options": {
                                      "authentication": {"required": False, "type": "str",
                                                         "choices": ["enable", "disable"]},
                                      "id": {"required": True, "type": "int"},
                                      "key": {"required": False, "type": "str"},
                                      "key-id": {"required": False, "type": "int"},
                                      "ntpv3": {"required": False, "type": "str",
                                                "choices": ["enable", "disable"]},
                                      "server": {"required": False, "type": "str"}
                                  }},
                    "ntpsync": {"required": False, "type": "str",
                                "choices": ["enable", "disable"]},
                    "server-mode": {"required": False, "type": "str",
                                    "choices": ["enable", "disable"]},
                    "source-ip": {"required": False, "type": "str"},
                    "syncinterval": {"required": False, "type": "int"},
                    "type": {"required": False, "type": "str",
                             "choices": ["fortiguard", "custom"]}
    
                }
            }
        }
    
        module = AnsibleModule(argument_spec=fields,
                               supports_check_mode=False)
        try:
            from fortiosapi import FortiOSAPI
        except ImportError:
            module.fail_json(msg="fortiosapi module is required")
    
        global fos
        fos = FortiOSAPI()
    
        is_error, has_changed, result = fortios_system(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    
    if __name__ == '__main__':
        main()


