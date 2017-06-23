kibana
======

[![Build Status](https://travis-ci.org/kbrebanov/ansible-kibana.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-kibana)

Installs and configures Kibana

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                           | Default                                      | Description                                                                                                                                                                                                                  |
|:-----------------------------------------------|:---------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| kibana_version                                 | 5.4.2                                        | Version of Kibana to install                                                                                                                                                                                                 |
| kibana_default_app_id                          | discover                                     | The default application to load.                                                                                                                                                                                             |
| kibana_i18n_default_locale                     | en                                           | The default locale (>= 5.0)                                                                                                                                                                                                  |
| kibana_index                                   | .kibana                                      | Kibana uses an index in Elasticsearch to store saved searches, visualizations and dashboards. Kibana creates a new index if the index doesn’t already exist.                                                                 |
| kibana_server_base_path                        | ''                                           | Specify a path to mount Kibana at if you are running behind a proxy. This setting cannot end in a slash.                                                                                                                     |
| kibana_server_host                             | 0.0.0.0                                      | Kibana backend server address                                                                                                                                                                                                |
| kibana_server_max_payload_bytes                | 1048576                                      | The maximum payload size in bytes for incoming server requests.                                                                                                                                                              |
| kibana_server_name                             | ''                                           | The Kibana server's name.  This is used for display purposes.                                                                                                                                                                |
| kibana_server_port                             | 5601                                         | Kibana backend server port                                                                                                                                                                                                   |
| kibana_server_ssl_cert                         | ''                                           | Path to the PEM-format SSL certificate file                                                                                                                                                                                  |
| kibana_server_ssl_enabled                      | false                                        | Enable SSL for outgoing requests from the Kibana server to the browser (>= 5.0)                                                                                                                                              |
| kibana_server_ssl_key                          | ''                                           | Path to the PEM-format SSL key file                                                                                                                                                                                          |
| kibana_elasticsearch_custom_headers            | {}                                           | Header names and values that are sent to Elasticsearch (>= 5.0)                                                                                                                                                              |
| kibana_elasticsearch_password                  | ''                                           | Elasticsearch basic auth password                                                                                                                                                                                            |
| kibana_elasticsearch_ping_timeout              | "{{ kibana_elasticsearch_request_timeout }}" | Time in milliseconds to wait for Elasticsearch to respond to pings                                                                                                                                                           |
| kibana_elasticsearch_preserve_host             | true                                         | When this setting’s value is true Kibana uses the hostname specified in the kibana_server_host setting. When the value of this setting is false, Kibana uses the hostname of the host that connects to this Kibana instance. |
| kibana_elasticsearch_request_headers_whitelist | [ authorization ]                            | List of Kibana client-side headers to send to Elasticsearch. To send *no* client-side headers, set this value to [] (an empty list). (>= 5.0)                                                                                |
| kibana_elasticsearch_request_timeout           | 300000                                       | Time in milliseconds to wait for responses from the back end or Elasticsearch. This must be a positive integer.                                                                                                              |
| kibana_elasticsearch_shard_timeout             | 0                                            | Time in milliseconds for Elasticsearch to wait for responses from shards. Set to 0 to disable                                                                                                                                |
| kibana_elasticsearch_ssl_ca                    | ''                                           | Path to the PEM-format SSL client certificate authority file                                                                                                                                                                 |
| kibana_elasticsearch_ssl_cert                  | ''                                           | Path to the PEM-format SSL client certificate file                                                                                                                                                                           |
| kibana_elasticsearch_ssl_key                   | ''                                           | Path to the PEM-format SSL client key file                                                                                                                                                                                   |
| kibana_elasticsearch_ssl_verification_mode     | full                                         | To disregard the validity of SSL certificates, change this setting's value to 'none' (>= 5.0)                                                                                                                                |
| kibana_elasticsearch_ssl_verify                | true                                         | To disregard the validity of SSL certificates, change this setting’s value to false. (< 5.0)                                                                                                                                 |
| kibana_elasticsearch_startup_timeout           | 5000                                         | Time in milliseconds to wait for Elasticsearch at Kibana startup before retrying                                                                                                                                             |
| kibana_elasticsearch_url                       | http://localhost:9200                        | The URL of the Elasticsearch instance to use for all your queries.                                                                                                                                                           |
| kibana_elasticsearch_username                  | ''                                           | Elasticsearch basic auth username                                                                                                                                                                                            |
| kibana_logging_dest                            | stdout                                       | Enables you specify a file where Kibana stores log output (>= 5.0)                                                                                                                                                           |
| kibana_logging_quiet                           | false                                        | Set the value of this setting to true to suppress all logging output other than error messages.                                                                                                                              |
| kibana_logging_silent                          | false                                        | Set the value of this setting to true to suppress all logging output.                                                                                                                                                        |
| kibana_logging_verbose                         | false                                        | Set the value of this setting to true to log all events, including system usage information and all requests.                                                                                                                |
| kibana_ops_interval                            | 5000                                         | Set the interval in milliseconds to sample system and process performance metrics. Minimum is 100ms                                                                                                                          |
| kibana_pid_file                                | ''                                           | Specifies the path where Kibana creates the process ID file (>= 5.0)                                                                                                                                                         |

Dependencies
------------

None

Example Playbook
----------------

Install Kibana
```yaml
- hosts: all
  roles:
    - kbrebanov.kibana
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
