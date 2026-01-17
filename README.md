# linux-monitoring-lab using grafana and prometheus.

This repository documents the implementation of monitoring tool step by step and troubleshooting process from a Linux administrator’s perspective.

### Why monitoring required.

In production Linux environments, system issues such as high CPU usage, memory leaks, disk exhaustion, or service failures must be detected early to prevent outages.

Monitoring helps to
- Identify resource bottlenecks
- Detect abnormal system behavior
- Troubleshoot incidents faster
- Provide visibility into system health

### what is being monitored for this setup

- cpu usage
- Memory utilisation
- Disk usage
- Network statistics
- System uptime and load

### componenets overview

**Node Exporter**

Node Exporter will collect the metrics from the system and expose it at port 9100

**Prometheus**

Periodically scrapes metrics from Node Exporter and stores them as time-series data.

**Grafana**

Visualisation dashboard to analyse the metrics.

### Architecture

Linux Host
 ├── Node Exporter (port 9100)
 ├── Prometheus (port 9090)
 └── Grafana (port 3000)

Prometheus scrapes metrics from Node Exporter.
Grafana queries Prometheus to display metrics.

### Ports Used

Node Exporter - 9100
Prometheus - 9090
Grafana - 3000
