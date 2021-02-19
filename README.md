# Ansible Role: ansible-apps_elasticsearch_exporter

## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_elasticsearch_exporter.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_elasticsearch_exporter)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_elasticsearch_exporter-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_elasticsearch_exporter)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_elasticsearch_exporter?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_elasticsearch_exporter)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_elasticsearch_exporter.svg)](https://github.com/lotusnoir/ansible-apps_elasticsearch_exporter/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_elasticsearch_exporter&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_elasticsearch_exporter)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_elasticsearch_exporter&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_elasticsearch_exporter)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_elasticsearch_exporter&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_elasticsearch_exporter)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_elasticsearch_exporter&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_elasticsearch_exporter)

Deploy [elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter) to expose elasticsearch metrics to prometheus.

## Role variables

| Name                             | Default Value         | Description                        |
| -------------------------------- | --------------------- | -----------------------------------|
| `es_exporter_version`            | 1.1.0                 | elasticsearch_exporter version |
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
