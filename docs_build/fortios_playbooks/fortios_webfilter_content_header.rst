================================
fortios_webfilter_content_header
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
      - name: Configure content types used by Web filter.
        fortios_webfilter_content_header:
          host:  "{{  host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{  vdom }}"
          webfilter_content_header:
            state: "present"
            comment: "Optional comments."
            entries:
             -
                action: "block"
                category: "<your_own_value>"
                pattern: "<your_own_value>"
            id:  "8"
            name: "default_name_9"



Playbook File Examples
----------------------

%%PB_FILE_EXAMPLE_TOKEN%%

