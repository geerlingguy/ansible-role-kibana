# Ansible Role: Kibana

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-kibana)

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    kibana_version: "4.6"

The version of kibana to install (major and minor only).

    kibana_server_port: 5601
    kibana_server_host: "0.0.0.0"

The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

    kibana_server_maxPayloadBytes: 1048576

The maximum payload size in bytes for incoming server requests.

    kibana_kibana_index: ".kibana"

The index Kibana uses in Elasticsearch to store saved searches, visualizations and dashboards. Kibana creates a new index if the index doesn’t already exist.

    kibana_kibana_defaultAppId: "discover"

The default application to load.

    kibana_elasticsearch_pingTimeout: 1500

Time in milliseconds to wait for Elasticsearch to respond to pings.

    kibana_elasticsearch_requestTimeout: 30000

Time in milliseconds to wait for responses from the back end or Elasticsearch. This value must be a positive integer.

    kibana_elasticsearch_shardTimeout: 0

Time in milliseconds for Elasticsearch to wait for responses from shards. Set to 0 to disable.

    kibana_elasticsearch_startupTimeout: 5000

Time in milliseconds to wait for Elasticsearch at Kibana startup before retrying.

    kibana_pid_file: /var/run/kibana.pid

The path where Kibana creates the process ID file.

    kibana_logging_dest: stdout

The file where Kibana stores log output.

    kibana_logging_silent: false

Set the value of this setting to true to suppress all logging output.

    kibana_logging_quiet: false

Set the value of this setting to true to suppress all logging output other than error messages.

    kibana_logging_verbose: false

Set the value of this setting to true to log all events, including system usage information and all requests.


## Dependencies

None.

## Example Playbook

    - hosts: kibana
      roles:
        - geerlingguy.kibana

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
