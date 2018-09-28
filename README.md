# Ansible Role: Kibana

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-kibana)

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    kibana_version: "6.x"

The version of kibana to install.

    kibana_service_state: started
    kibana_service_enabled: true

Controls whether the `kibana` service is started and enabled on system boot.

    kibana_config_file_path: /etc/kibana/kibana.yml

The path to the Kibana configuration file.

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

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
