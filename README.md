# Ansible Role: Kibana

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-kibana)

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

The TLS status of Kibana.

    kibana_server_ssl_enabled: false

The server certificate and private keys paths or path to PKCS#12 file where your server certificate and private key are contained.

    kibana_server_ssl_certificate_path: ""
    kibana_server_ssl_key_path: ""

    kibana_server_ssl_keystore_path: ""

The PKCS#12 decryption password.
    
    kibana_server_ssl_keystore_password: ""

The Elasticsearch CA certificate for Kibana to trust.
    
    kibana_elasticsearch_ssl_certificate_authorities_path: ""

The verification of the server certificate that Kibana receives when making an outbound SSL/TLS connection to Elasticsearch.

    kibana_elasticsearch_ssl_verification_mode: ""

If Elasticsearch is protected by HTTP basic authentication, set the username and password so Kibana can connect.

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
