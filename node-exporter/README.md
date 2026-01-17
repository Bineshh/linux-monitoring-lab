Node Exporter Setup using Podman

This doc is to describe the installation and configuration of Node exporter using Podman.

Node-Exporter exposes Linux system metrics (CPU, Memory) which are sraped by prometheus and visualised by grafana.

Architecture Role:

Linux Host
│
├── Node Exporter (9100)
│       ↑
│   Prometheus (9090)
│       ↑
│    Grafana (3000)


step 1 : run the command to configure the node-exporter

podman run -d --name node-exporter -p 9100:9100 --network monitoring_net prom/node-exporter:latest

step 2 : check podman status

podman ps

step 3 : visit URL and confirm it's exposing the data

http://localhost:9100/metrics


