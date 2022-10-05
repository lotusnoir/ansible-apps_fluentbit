# ansible-apps_fluentbit

## Description

[![Galaxy Role](https://img.shields.io/badge/galaxy-apps_fluentbit-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_fluentbit.svg)](https://github.com/lotusnoir/ansible-apps_fluentbit/releases/latest)
[![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_fluentbit?color=orange&style=flat)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
[![downloads](https://img.shields.io/ansible/role/d/56084)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/56084)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)

Deploy [fluentbit](https://fluentbit.io/) log forwarder system using ansible.

## Requirements

none

## Role variables

See [variables](/defaults/main.yml) for more details.

## Examples

        ---
        - hosts: apps_fluentbit
          become: true
          become_method: sudo
          gather_facts: true
          roles:
            - role: ansible-apps_fluentbit
          vars:
            fluentbit_inputs:
              - name: tail
                alias: vms
                tag: vms
                path: /tmp/vms.log
                db: /tmp/vms.db
                parser: syslog
            fluentbit_filters:
              - name: modify
                alias: add_from_syslog
                match: '*'
                type: Add
                value: 'from_syslog true'
            fluentbit_outputs:
              - name: null
                match: '*'
            fluentbit_parsers:
              - name: syslog
                format: regex
                regex: '^(?<register_time>[^ ]*) (?<source>[^ ]*) (?<level>[^ ]*) *(?<message>.*)$'
                time_key: time
                time_format: '%Y-%m-%dT%H:%M:%S %z'
                time_keep: on



## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.

