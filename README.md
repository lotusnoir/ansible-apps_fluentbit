# Ansible Role: ansible-apps_fluentbit


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_fluentbit.svg?branch=master)](https://travis-ci.com/lotusnoir/ansible-apps_fluentbit)[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__fluentbit-blue)](https://galaxy.ansible.com/lotusnoir/ansible-apps_fluentbit/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/ansible-apps_fluentbit/tags)

Deploy [fluentbit](https://fluentbit.io/) log forwarder system using ansible.

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `fluentbit_version` | 1.5.6 | fluentbit package version |
| `fluentbit_install_dir` | /etc/fluentbit | fluentbit config directory |

## Examples

	---
	- hosts: apps_fluentbit
	  become: yes
	  become_method: sudo
	  gather_facts: yes
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
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
