# Ansible Role: ansible-apps_fluentbit


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_fluentbit.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_fluentbit)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_fluentbit-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_fluentbit?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_fluentbit)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_fluentbit.svg)](https://github.com/lotusnoir/ansible-apps_fluentbit/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_fluentbit&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_fluentbit)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_fluentbit&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_fluentbit)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_fluentbit&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_fluentbit)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_fluentbit&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_fluentbit)

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

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
