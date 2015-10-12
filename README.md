kibana
======

Installs and configures Kibana

Requirements
------------

This role requires Ansible 1.6 or higher.

Role Variables
--------------

| Name                               | Default                                                          | Description                                                                                     |
|------------------------------------|------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| kibana_version                     | 4.1.2                                                            | Version of Kibana to install                                                                    |
| kibana_sha256sum                   | 5f6213f7ac7ef71016a6750f09e7316ccc9bca139bc5389b417395b179bc370c | SHA 256 checksum of archive                                                                     |
| kibana_port                        | 5601                                                             | Kibana server port                                                                              |
| kibana_host_bind                   | "0.0.0.0"                                                        | The host to bind the server to                                                                  |
| kibana_elasticsearch_url           | "http://localhost:9200"                                          | The Elasticsearch instance to use                                                               |
| kibana_elasticsearch_preserve_host | true                                                             | If enabled, sends the hostname specified in Elasticsearch                                       |
| kibana_elasticsearch_index         | ".kibana"                                                        | Index name in Elasticsearch                                                                     |
| kibana_elasticsearch_username      | ''                                                               | Elasticsearch basic auth username                                                               |
| kibana_elasticsearch_password      | ''                                                               | Elasticsearch basic auth password                                                               |
| kibana_elasticsearch_client_crt    | ''                                                               | Elasticsearch client certificate                                                                |
| kibana_elasticsearch_client_key    | ''                                                               | Elasticsearch client key                                                                        |
| kibana_ca                          | ''                                                               | Elasticsearch CA certificate                                                                    |
| kibana_default_app_id              | "discover"                                                       | The default application to load                                                                 |
| kibana_request_timeout             | 300000                                                           | Time in milliseconds to wait for responses from the back end or Elasticsearch. This must be > 0 |
| kibana_ping_timeout                | "{{ kibana_request_timeout }}"                                   | Time in milliseconds to wait for Elasticsearch to respond to pings                              |
| kibana_shard_timeout               | 0                                                                | Time in milliseconds for Elasticsearch to wait for responses from shards. Set to 0 to disable   |
| kibana_startup_timeout             | 0                                                                | Time in milliseconds to wait for Elasticsearch at Kibana startup before retrying                |
| kibana_verify_ssl                  | true                                                             | Set to false to have a complete disregard for the validity of the SSL certificate               |
| kibana_ssl_key_file                | ''                                                               | SSL key for outgoing requests from the Kibana Server                                            |
| kibana_ssl_cert_file               | ''                                                               | SSL cert for outgoing requests from the Kibana Server                                           |

Dependencies
------------

None

Example Playbook
----------------

Install Kibana
```
- hosts: all
  roles:
    - { role: kbrebanov.kibana }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
