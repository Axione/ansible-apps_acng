# Ansible Role: apps_acng

## Description

[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_alerta-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_alerta)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_acng?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_alerta)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_acng.svg)](https://github.com/lotusnoir/ansible-apps_acng/releases/latest)

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_acng&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_acng)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_acng&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_acng)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_acng&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_acng)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_acng&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_acng)


Deploy apt-cacher-ng cache system using ansible.

## Requirements

none

## Role variables

| Name                      | Default Value | Description                        |
| ------------------------- | ------------- | -----------------------------------|
| `acng_bindaddress`        | 0.0.0.0 | acng bind listen address |
| `acng_port`               | 3142 | acng listen port |
| `acng_cache_dir`          | /var/cache/apt-cacher-ng | Sources cache directory |
| `acng_log_dir`            | /var/log/apt-cacher-ng | log directory |
| `acng_use_proxy`          | true | use proxy to acces internet |
| `acng_proxy`              | "" | proxy address if in use |
| `acng_ExThreshold`        | 4 | Days before considering an unreferenced file expired (to be deleted) |
| `acng_ReuseConnections`   | 0 | Keep outgoing connections alive and reuse them for later downloads from the same server as long as possible |
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
