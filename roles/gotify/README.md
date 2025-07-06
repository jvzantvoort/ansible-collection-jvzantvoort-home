Gotify Role
===========

This Ansible role installs and configures [Gotify](https://gotify.net/), a
simple server for sending and receiving messages in real time, on your target
hosts.

Requirements
------------

- Ansible 2.15 or higher
- Target system: EL
- Python 3 on the target host

Role Variables
--------------

Available variables are listed below, along with their default values (see `defaults/main.yml` for the full list):

```yaml
gotify_version: "2.4.0"                # Version of Gotify to install
gotify_user: "gotify"                   # System user to run Gotify
gotify_group: "gotify"                  # System group for Gotify
gotify_install_dir: "/opt/gotify"       # Installation directory
gotify_data_dir: "/var/lib/gotify"      # Data directory
gotify_port: 8080                       # Port for Gotify web interface
gotify_binary_url: ""                   # Custom URL for Gotify binary (optional)
gotify_config: {}                       # Extra configuration options (see Gotify docs)
```

You can override these variables in your playbook or inventory as needed.

Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

```yaml
- hosts: servers
  become: true
  tasks:
    - name: Install gotify
      ansible.builtin.include_role:
        name: jvzantvoort.home.gotify
      vars:
        gotify_database_admin_password: "password"
        gotify_database_admin_username: "root"

```

License
-------

GPL-2.0-or-later

Author Information
------------------

John van Zantvoort