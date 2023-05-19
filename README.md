# ansible-apps_acng

[![Galaxy Role](https://img.shields.io/badge/galaxy-apps_acng-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_acng)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_acng.svg)](https://github.com/lotusnoir/ansible-apps_acng/releases/latest)
[![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_acng?color=orange&style=flat)](https://galaxy.ansible.com/lotusnoir/apps_acng)
[![downloads](https://img.shields.io/ansible/role/d/56111)](https://galaxy.ansible.com/lotusnoir/apps_acng)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/56111)](https://galaxy.ansible.com/lotusnoir/apps_acng)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)

## Description

Install and configure apt-cacher-ng
## Requirements

none

## Role variables

See [variables](/defaults/main.yml) for more details.

## Examples

        ---
        - hosts: apps_acng
          become: true
          become_method: sudo
          gather_facts: true
          roles:
            - role: ansible-apps_acng
          vars:
            acng_cache_dir: "/data/apt-cacher/"
            acng_use_proxy: false



## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.

## Author Information

- [Philippe LEAL](https://github.com/lotusnoir)
