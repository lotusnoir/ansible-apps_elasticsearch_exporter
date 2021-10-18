# ansible-apps_elasticsearch_exporter

## Description

[![Galaxy Role](https://img.shields.io/badge/galaxy-apps_acng-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_acng)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_acng.svg)](https://github.com/lotusnoir/ansible-apps_acng/releases/latest)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_acng?color=orange&style=flat)
[![downloads](https://img.shields.io/ansible/role/d/52265)](https://galaxy.ansible.com/lotusnoir/apps_acng)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52265)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)

Deploy [elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter) to expose elasticsearch metrics to prometheus.

## Role variables

| Name                             | Default Value         | Description                        |
| -------------------------------- | --------------------- | -----------------------------------|
| `es_exporter_version`            | 1.2.1                 | elasticsearch_exporter version |
| `es_exporter_temp_dir`           | /tmp                  | temporary directory to uncompress package |
| `es_exporter_install_dir`        | /usr/local/bin        | directory to install binary |
| `es_exporter_force_install`      | false                 | force install variable |
| `es_exporter_es_uri`             | http://localhost:9200 | elasticsearch web address |
| `es_exporter_web_listen_port`    | :9123                 | elasticsearch_exporter exposed port |
| `es_exporter_web_telemetry_path` | /metrics              | elasticsearch_exporter metrics path |
| `es_exporter_es_all`             | false                 | expose all metrics |
| `es_exporter_es_indices`         | false                 | expose indices metrics |
| `es_exporter_es_shards`          | false                 | expose shards metrics |
| `es_exporter_es_ssl_skip_verify` | false                 | elasticsearch_exporter skip ssl on elasticsearch web connection |
| `es_exporter_es_timeout`         | 5s                    | elasticsearch_exporter timeout |

## Examples

	---
	- hosts: apps_elasticsearch_exporter
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_elasticsearch_exporter
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## Prometheus rules

TODO

## Grafana Dashboard

A sample dashboard is available here: [https://grafana.com/grafana/dashboards/13562](https://grafana.com/grafana/dashboards/13562)

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
