Grafana Setup using Podman 

Overview

This doc is to describe the installation and configuration of grafana using podman containers.
Grafana used to visualise the metrics collected from prometheus 


Architecture

+------------------+
| Linux Host       |
|                  |
| Podman Network   |
| monitoring-net   |
|     |      |     |
| Prometheus  Grafana
|  :9090      :3000
+------------------+


step 1 : Create a grafana directory

mkdir -p ~/monitoring/grafana/data

step 2 : run the command:

podman run -d --name grafana -p 3000:3000 -v ~/monitoring/grafana/data:/var/lib/grafana:Z --network monitoring_net grafana/grafana

step 3 : verify grafana

podman ps

step 4 : confirm logs no issues

podman logs -f grafana

step 5 : Access UI 

http://localhost:3000

step 6 : Add prometheus as data source and configure the prometheus URL 

step 7 : once node-exporter is configured , live data will be shown here 
