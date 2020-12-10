# Ansible Role: acng


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_acng.svg?branch=master)](https://travis-ci.com/lotusnoir/ansible-apps_acng)[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen)](https://opensource.org/licenses/Apache-2.0)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__acng-blue)](https://galaxy.ansible.com/lotusnoir/ansible-apps_acng/)[![GitHub Version](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/ansible-apps_acng/tags)

Deploy apt-cacher-ng cache system using ansible.

## Requirements

none

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `acng_bindaddress` | 0.0.0.0 | acng bind listen address |
| `acng_port` | 3142 | acng listen port |
| `acng_cache_dir` | /var/cache/apt-cacher-ng | Sources cache directory |
| `acng_log_dir` | /var/log/apt-cacher-ng | log directory |
| `acng_use_proxy` | true | use proxy to acces internet |
| `acng_proxy` | "" | proxy address if in use |
| `acng_ExThreshold` | 4 | Days before considering an unreferenced file expired (to be deleted) |
| `acng_ReuseConnections` | 0 | Keep outgoing connections alive and reuse them for later downloads from the same server as long as possible |
| `acng_PassThroughPattern` | '.*' | allow data pass-through mode for certain hosts when requested by the client using a CONNECT request |

## Examples

	---
	- hosts: apps_acng
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_acng
	  vars:
        acng_cache_dir: "/data/apt-cacher/"
        acng_use_proxy: true
        acng_proxy: "{{ http_proxy }}"
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}


## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
