# zynomi-log-core

Log aggregator and vizualization setup using Grafana, Loki and Promtail

## Pre-requisite

- Docker engine
- Should know how to setup `loki` as datasource
- LogQL language

## Setup procedure

- clone the repo
- cd to `zynomi-log-core` root folder
- create docker network as `docker network create loki`
- Edit `loki` service in `docker-compose.yml`
  - To mount your local directory where the `loki` config is located
- Edit `promtail` service in `docker-compose.yml`
  - To `mount` your local directory contains the logs to be scrapped
  - To mount your local directory where the `promtail` config is located
- Edit `grafana` service in `docker-compose.yml`
  - To mount your local director where grafana will store its database files & folder
- run `docker-compose up -d` or `docker-compose down`
- open grafana web app `http://localhost:3000`

## Known Issues

- Stopping loki takes longer time so be patience

## References

- [Meet Grafana LOKI, a Log Aggregation System for EVERYTHING](https://www.youtube.com/watch?v=h_GGd7HfKQ8)
- How to setup slack notification using [Slack Webhook](https://www.youtube.com/watch?v=yWzxbG3YDcM)
- Free Webhook testers online
  - [WebHook.Site](https://webhook.site/)
  - [RequestBin](https://requestbin.com/)
