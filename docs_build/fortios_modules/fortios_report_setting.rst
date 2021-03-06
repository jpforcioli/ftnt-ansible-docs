======================
fortios_report_setting
======================


Metadata
--------




**Name:** fortios_report_setting

**Description:** This module is able to configure a FortiGate or FortiOS by allowing the user to set and modify report feature and setting category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.2


**Author(s):** 

- Miguel Angel Munoz (github: @mamunozgonzalez)

- Nicolas Thomas (github: @thomnico)



**Ansible Version Added/Required:** 2.8

**Dev Status:** No status updates, yet. Contact Authors.

Parameters
----------

host
++++

- Description: FortiOS or FortiGate ip address.

  

- Required: True

https
+++++

- Description: Indicates if the requests towards FortiGate must use HTTPS protocol

  

- default: True

password
++++++++

- Description: FortiOS or FortiGate password.

  

- default: 

report_setting
++++++++++++++

- Description: Report setting configuration.

  

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
    
    

- filter_report_setting_data

 .. code-block:: python

    def filter_report_setting_data(json):
        option_list = ['fortiview', 'pdf-report', 'report-source',
                       'top-n', 'web-browsing-threshold']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    

- flatten_multilists_attributes

 .. code-block:: python

    def flatten_multilists_attributes(data):
        multilist_attrs = []
    
        for attr in multilist_attrs:
            try:
                path = "data['" + "']['".join(elem for elem in attr) + "']"
                current_val = eval(path)
                flattened_val = ' '.join(elem for elem in current_val)
                exec(path + '= flattened_val')
            except BaseException:
                pass
    
        return data
    
    

- report_setting

 .. code-block:: python

    def report_setting(data, fos):
        vdom = data['vdom']
        report_setting_data = data['report_setting']
        flattened_data = flatten_multilists_attributes(report_setting_data)
        filtered_data = filter_report_setting_data(flattened_data)
        return fos.set('report',
                       'setting',
                       data=filtered_data,
                       vdom=vdom)
    
    

- fortios_report

 .. code-block:: python

    def fortios_report(data, fos):
        login(data)
    
        if data['report_setting']:
            resp = report_setting(data, fos)
    
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
            "https": {"required": False, "type": "bool", "default": True},
            "report_setting": {
                "required": False, "type": "dict",
                "options": {
                    "fortiview": {"required": False, "type": "str",
                                  "choices": ["enable", "disable"]},
                    "pdf-report": {"required": False, "type": "str",
                                   "choices": ["enable", "disable"]},
                    "report-source": {"required": False, "type": "str",
                                      "choices": ["forward-traffic", "sniffer-traffic", "local-deny-traffic"]},
                    "top-n": {"required": False, "type": "int"},
                    "web-browsing-threshold": {"required": False, "type": "int"}
    
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
    
        is_error, has_changed, result = fortios_report(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    



Module Source Code
------------------

.. code-block:: python

    #!/usr/bin/python
    from __future__ import (absolute_import, division, print_function)
    # Copyright 2019 Fortinet, Inc.
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
    module: fortios_report_setting
    short_description: Report setting configuration in Fortinet's FortiOS and FortiGate.
    description:
        - This module is able to configure a FortiGate or FortiOS by allowing the
          user to set and modify report feature and setting category.
          Examples include all parameters and values need to be adjusted to datasources before usage.
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
                - FortiOS or FortiGate ip address.
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
            default: true
        report_setting:
            description:
                - Report setting configuration.
            default: null
            suboptions:
                fortiview:
                    description:
                        - Enable/disable historical FortiView.
                    choices:
                        - enable
                        - disable
                pdf-report:
                    description:
                        - Enable/disable PDF report.
                    choices:
                        - enable
                        - disable
                report-source:
                    description:
                        - Report log source.
                    choices:
                        - forward-traffic
                        - sniffer-traffic
                        - local-deny-traffic
                top-n:
                    description:
                        - Number of items to populate (100 - 4000).
                web-browsing-threshold:
                    description:
                        - Web browsing time calculation threshold (3 - 15 min).
    '''
    
    EXAMPLES = '''
    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
      tasks:
      - name: Report setting configuration.
        fortios_report_setting:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          report_setting:
            fortiview: "enable"
            pdf-report: "enable"
            report-source: "forward-traffic"
            top-n: "6"
            web-browsing-threshold: "7"
    '''
    
    RETURN = '''
    build:
      description: Build number of the fortigate image
      returned: always
      type: str
      sample: '1547'
    http_method:
      description: Last method used to provision the content into FortiGate
      returned: always
      type: str
      sample: 'PUT'
    http_status:
      description: Last result given by FortiGate on last operation applied
      returned: always
      type: str
      sample: "200"
    mkey:
      description: Master key (id) used in the last call to FortiGate
      returned: success
      type: str
      sample: "id"
    name:
      description: Name of the table used to fulfill the request
      returned: always
      type: str
      sample: "urlfilter"
    path:
      description: Path of the table used to fulfill the request
      returned: always
      type: str
      sample: "webfilter"
    revision:
      description: Internal revision number
      returned: always
      type: str
      sample: "17.0.2.10658"
    serial:
      description: Serial number of the unit
      returned: always
      type: str
      sample: "FGVMEVYYQT3AB5352"
    status:
      description: Indication of the operation's result
      returned: always
      type: str
      sample: "success"
    vdom:
      description: Virtual domain used
      returned: always
      type: str
      sample: "root"
    version:
      description: Version of the FortiGate
      returned: always
      type: str
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
    
    
    def filter_report_setting_data(json):
        option_list = ['fortiview', 'pdf-report', 'report-source',
                       'top-n', 'web-browsing-threshold']
        dictionary = {}
    
        for attribute in option_list:
            if attribute in json and json[attribute] is not None:
                dictionary[attribute] = json[attribute]
    
        return dictionary
    
    
    def flatten_multilists_attributes(data):
        multilist_attrs = []
    
        for attr in multilist_attrs:
            try:
                path = "data['" + "']['".join(elem for elem in attr) + "']"
                current_val = eval(path)
                flattened_val = ' '.join(elem for elem in current_val)
                exec(path + '= flattened_val')
            except BaseException:
                pass
    
        return data
    
    
    def report_setting(data, fos):
        vdom = data['vdom']
        report_setting_data = data['report_setting']
        flattened_data = flatten_multilists_attributes(report_setting_data)
        filtered_data = filter_report_setting_data(flattened_data)
        return fos.set('report',
                       'setting',
                       data=filtered_data,
                       vdom=vdom)
    
    
    def fortios_report(data, fos):
        login(data)
    
        if data['report_setting']:
            resp = report_setting(data, fos)
    
        fos.logout()
        return not resp['status'] == "success", resp['status'] == "success", resp
    
    
    def main():
        fields = {
            "host": {"required": True, "type": "str"},
            "username": {"required": True, "type": "str"},
            "password": {"required": False, "type": "str", "no_log": True},
            "vdom": {"required": False, "type": "str", "default": "root"},
            "https": {"required": False, "type": "bool", "default": True},
            "report_setting": {
                "required": False, "type": "dict",
                "options": {
                    "fortiview": {"required": False, "type": "str",
                                  "choices": ["enable", "disable"]},
                    "pdf-report": {"required": False, "type": "str",
                                   "choices": ["enable", "disable"]},
                    "report-source": {"required": False, "type": "str",
                                      "choices": ["forward-traffic", "sniffer-traffic", "local-deny-traffic"]},
                    "top-n": {"required": False, "type": "int"},
                    "web-browsing-threshold": {"required": False, "type": "int"}
    
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
    
        is_error, has_changed, result = fortios_report(module.params, fos)
    
        if not is_error:
            module.exit_json(changed=has_changed, meta=result)
        else:
            module.fail_json(msg="Error in repo", meta=result)
    
    
    if __name__ == '__main__':
        main()


