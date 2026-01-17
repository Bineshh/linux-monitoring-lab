### ProMetheus Monitoring setup using podman

Overview

This repo documents the installtion and configuration of prometheus using podman containers.

step 1 : Create podman network 

A dedicated podman bridge network to let containers talk to each other.

podman create network monitoring_net

step 2 : Prometheus configuration and create a yaml file to scrap the data

mkdir -p ~/monitoring/prometheus
vim prometheus.yaml

step 3 : pull the image and run.

podman run -d --name prometheus -v ~/monitoring/prometheus/prometheus.yaml:/etc/prometheus/prometheus.yaml:Z --network monitoring_net -p 9090:9090 prom/prometheus:latest

step 4 : verify container is working and check for errors

podman logs -f prometheus
podman ps --> look for port configuration and running status

step 5 : Access Prometheus UI and check the active status (UP)

http://localhost:9090 



