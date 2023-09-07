# Ansible Role: Kibana

[![CI](https://github.com/geerlingguy/ansible-role-kibana/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-kibana/actions?query=workflow%3ACI)

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    kibana_version: "7.x"

The version of kibana to install.

    kibana_package: kibana
    kibana_package_state: present

The specific package to be installed. You can specify a version of the package using the correct syntax for your platform and package manager by changing the package name. You can also control the package state (e.g. `present`, `absent`, or `latest`).

    kibana_service_state: started
    kibana_service_enabled: true

Controls whether the `kibana` service is started and enabled on system boot.

    kibana_config_template: kibana.yml.j2
    kibana_config_file_path: /etc/kibana/kibana.yml

The template to use for the Kibana config file, and the path to which the config file will be written.

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

    kibana_elasticsearch_username: ""
    kibana_elasticsearch_password: ""

If Elasticsearch is protected by HTTP basic authentication, set the username and password so Kibana can connect.

    kibana_extra_options: ''

A placeholder for arbitrary configuration options not exposed by the role. This will be appended as-is to the end of the kibana.yml file, as long as your variable preserves formatting with a |. For example:

    kibana_extra_options: |  # Dont forget the pipe!
        some.option: true
        another.option: false

## Dependencies

None.

## Example Playbook

    - hosts: kibana
      roles:
        - geerlingguy.kibana

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
