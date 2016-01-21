# Ansible Role: Kibana

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-kibana)

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

  - This role was made to work with Nginx; other HTTP servers are not supported at this time.
  - On RedHat-based distributions, the `python-passlib` library is required, which is available through the EPEL repository. You can enable EPEL by adding the `geerlingguy.repo-epel` role to your playbook.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    workspace: /root

A workspace where Kibana's download will be stored while configuring Kibana.

    kibana_root: /var/www/kibana3

The location of Kibana's base install.

    kibana_version: 3.1.2

The version of kibana to install.

    kibana_server_name: logs.example.com

The FQDN or IP address of the Kibana server.

    kibana_elasticsearch_port: 80

The port where Kibana will connect to Elasticsearch.

    kibana_username: kibana
    kibana_password: password

Kibana basic HTTP authentication username and password. Please override these with secure credentials!

    kibana_password_protect_all: false

If set to `false` (default), only Kibana configuration resulting in persistent changes (saving or loading dashboards, for example) will be password protected. If set to `true`, *all* of Kibana will require password protection via Nginx HTTP basic authentication.

## Dependencies

  - geerlingguy.nginx
  - geerlingguy.repo-epel (RedHat/CentOS only)

## Example Playbook

    - hosts: search
      roles:
        - { role: geerlingguy.nginx }
        - { role: geerlingguy.kibana }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
