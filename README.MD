# Ansible WordPress Role

This repository contains an Ansible role to install and configure WordPress with Apache and MySQL. It includes Molecule tests for automated validation across multiple Linux distributions.
## Features

    Installs WordPress in a configurable directory.

    Configures Apache virtual hosts for WordPress.

    Manages MySQL database and user for WordPress.

    Includes Molecule scenarios for Debian, Ubuntu, and Oracle Linux.

    Uses best practices with Ansible Role dependencies.

    Supports idempotent and testable infrastructure automation.

## Requirements

    Ansible 2.12+ (or specified minimum in meta/main.yml)

    Docker (for Molecule testing)

    Python 3.x environment with ansible and molecule installed

    MySQL server accessible to configure WordPress database

## Usage

    Clone this repository or include the wordpress role in your Ansible project.

    Define your playbook, for example:
```
- name: Deploy WordPress
  hosts: all
  become: true
  vars:
    wordpress_db_name: wp_db
    wordpress_db_user: wp-user
    wordpress_db_password: wp-pass
    wordpress_apache_server_name: localhost
    wordpress_dir: "/var/www/{{ wordpress_apache_server_name }}"
  roles:
    - wordpress
```
## Run the playbook:
```
ansible-playbook -i inventory your-playbook.yml
```
Directory structure
```
roles/
└── wordpress/
    ├── tasks/
    ├── handlers/
    ├── templates/
    ├── vars/
    ├── defaults/
    ├── molecule/
    ├── meta/
    └── README.md
```

This project is licensed under the MIT License.
