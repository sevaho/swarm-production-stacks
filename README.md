# The Great Docker Swarm production stacks

> This Repo is under construction!

> description TODO

<!-- vim-markdown-toc Marked -->

* [Goals](#goals)
    * [Principles](#principles)
* [Stacks](#stacks)
    * [monitoring](#monitoring)
    * [logging](#logging)
    * [ci_cd](#ci_cd)
    * [web_proxy](#web_proxy)
    * [git](#git)
    * [database_postgres](#database_postgres)
    * [database_mongodb](#database_mongodb)
    * [webdav](#webdav)
    * [caldav](#caldav)
    * [container_registry](#container_registry)
    * [vault](#vault)
    * [container_updates](#container_updates)

<!-- vim-markdown-toc -->

## Goals

### Principles

- docker-compose 3.7
- docker volumes over own path
- docker secrets over env_paths, and env_paths over envs
- a stack should work out of the box with 1 env folder or templater
- first class logging and monitoring support

## Stacks


```
                            letsencrypt
                             | 
INTERNET ----> HAproxy ---> Traefik  ----- (all)

```

### monitoring

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| grafana       | Monitoring and metrics analytics | [github](https://github.com/grafana/grafana)              | [ ]  |
| prometheus    | Monitoring manager               | [github](https://github.com/prometheus/prometheus)        | [ ]  |
| alertmanager  | Alert manager                    | [github](https://github.com/prometheus/alertmanager)      | [ ]  |
| cadvisor      | Container metrics                | [github](https://github.com/google/cadvisor)              | [ ]  |
| node-exporter | Hardware and OS metrics          | [github](https://github.com/prometheus/node_exporter)     | [ ]  |
| blackbox      | HTTP endpoint probing            | [github](https://github.com/prometheus/blackbox_exporter) | [ ]  |
| alerta        | Alert visualizer                 | [github](https://github.com/alerta/alerta)                | [ ]  |

### logging

| Container              | Description                      | Links                                                            | Done |
| -------------          | -------------------------------- | ---------------------------------------------------------        | ---- |
| fluentd                | Logging collector                | [github](https://github.com/fluent/fluentd)                      | [ ]  |
| Kibana                 | Logging analytics dashboard      | [github](https://github.com/elastic/kibana)                      | [ ]  |
| Elasticsearch          | Logging search engine            | [github](https://github.com/elastic/elasticsearch)               | [ ]  |
| Elasticsearch_exporter | Elastic search metrics           | [github](https://github.com/justwatchcom/elasticsearch_exporter) | [ ]  |

### ci_cd

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| drone         | CI/CD platform                   | [github](https://github.com/drone/drone)                  | [ ]  |
| drone_vault   | Vault extension for drone        | [github](https://github.com/drone/drone-vault)            | [ ]  |

### web_proxy

| Container     | Description                          | Links                                                     | Done |
| ------------- | --------------------------------     | --------------------------------------------------------- | ---- |
| haproxy       | Load balancer                        | [github](https://github.com/haproxy/haproxy)              | [ ]  |
| traefik       | Http reverse proxy and load balancer | [github](https://github.com/containous/traefik)           | [ ]  |

### git

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| gitea         | Self-hosted git service          | [github](https://github.com/go-gitea/gitea)               | [ ]  |

### database_postgres

| Container         | Description                      | Links                                                     | Done |
| -------------     | -------------------------------- | --------------------------------------------------------- | ---- |
| postgres          | PostgresQL database              | [github](https://github.com/postgres/postgres)            | [ ]  |
| postgres_exporter | PostgresQL database exporter     | [github](https://github.com/wrouesnel/postgres_exporter)  | [ ]  |

### database_mongodb

| Container         | Description                      | Links                                                     | Done |
| -------------     | -------------------------------- | --------------------------------------------------------- | ---- |
| mongodb           | MongoDB database                 | [github](https://github.com/mongodb/mongo)                | [ ]  |
| mongodb_exporter | MongoDB database exporter     | [github](https://github.com/percona/mongodb_exporter)     | [ ]  |

### webdav

| Container          | Description                        | Links                                                       | Done |
| -------------      | --------------------------------   | ---------------------------------------------------------   | ---- |
| nextcloud          | Self-hosted cloud-service          | [github](https://github.com/nextcloud/server)               | [ ]  |
| nextcloud_exporter | Self-hosted cloud-service exporter | [github](https://github.com/xperimental/nextcloud-exporter) | [ ]  |

### caldav

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| radicale      | Self-hosted caldav server        | [github](https://github.com/Kozea/Radicale)               | [ ]  |

### container_registry

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| registry      | Docker container registry        | [github](https://github.com/docker/distribution)          | [ ]  |

### vault

| Container      | Description                      | Links                                                     | Done |
| -------------  | -------------------------------- | --------------------------------------------------------- | ---- |
| vault          | Secret manager                   | [github](https://github.com/hashicorp/vault)              | [ ]  |
| vault_exporter | Secret manager exporter          | [github](https://github.com/grapeshot/vault_exporter)     | [ ]  |

### container_updates

| Container     | Description                      | Links                                                     | Done |
| ------------- | -------------------------------- | --------------------------------------------------------- | ---- |
| watchtower    | Automating container updates     | [github](https://github.com/containrrr/watchtower)        | [ ]  |
