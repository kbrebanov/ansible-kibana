kibana
======

Installs and configures Kibana

Requirements
------------

This role requires Ansible 1.6 or higher.

Role Variables
--------------

| Name                     | Default                                                          | Description                       |
|--------------------------|------------------------------------------------------------------|-----------------------------------|
| kibana_version           | 4.1.1                                                            | Version of Kibana to install      |
| kibana_sha256sum         | 6f42d25f337fd49f38e2af81b9ab6e0c987a199a8c0b2e1410d072f812cb4520 | SHA 256 checksum of archive       |
| kibana_port              | 5601                                                             | Kibana server port                |
| kibana_host_bind         | "0.0.0.0"                                                        | The host to bind the server to    |
| kibana_elasticsearch_url | "http://localhost:9200"                                          | The Elasticsearch instance to use |

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
