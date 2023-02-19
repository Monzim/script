# Monitoring System

This is a Docker Compose configuration for setting up a simple monitoring system with Prometheus and Grafana. The monitoring system also includes node_exporter for monitoring the host system and cAdvisor for monitoring Docker containers.

## **Requirements**

- Docker
- Docker Compose

## **Installation**

1. Clone this repository: **`https://github.com/Monzim/script.git`**
2. Navigate to the cloned directory: **`cd docker-compose/monitoring`**
3. Create the necessary data directories for Prometheus and Grafana:

   ```bash
   mkdir -p ~/monitoringSystemData/prometheus
   mkdir -p ~/monitoringSystemData/grafana
   sudo cp docker-compose/monitoring/prometheus/prometheus.yml /etc/prometheus/
   ```

4. Start the monitoring system: **`docker compose up -d`**

## **Services**

The monitoring system consists of the following services:

- **Prometheus:** A time-series database and alerting system for collecting and storing metrics from various sources.
- **Grafana:** A platform for creating and sharing dashboards and visualizations based on data from various sources.
- **node_exporter:** An exporter for collecting host-level metrics such as CPU usage, memory usage, and disk usage.
- **cAdvisor:** An agent for collecting performance metrics about running Docker containers.

## **Usage**

The monitoring system includes the following services:

- Prometheus: available at **`http://localhost:9090`**
- Grafana: available at **`http://localhost:3000`**. Login with username **`admin`** and password **`admin`**.
- Node Exporter: collects system metrics from the host machine.
- cAdvisor: collects container metrics.

## **Configuration**

### **Prometheus**

Prometheus is configured using the **`prometheus.yml`** file located in the **`/etc/prometheus`** directory on the host machine. This file can be edited to add or remove metrics to be scraped.

### **Grafana**

Grafana is configured using the web interface available at **`http://localhost:3000`**. Login with username **`admin`** and password **`admin`**. Once logged in, you can create or import dashboards and customize the data sources.

### **Node Exporter**

Node Exporter is configured using the **`--path.rootfs`** flag in the **`docker-compose.yml`** file. By default, it is set to **`/host`**.

### **cAdvisor**

cAdvisor is configured using various mounts and devices in the **`docker-compose.yml`** file. These mounts allow cAdvisor to collect metrics from the host machine and Docker containers.

## **Data Persistence**

Prometheus and Grafana data are stored in the **`~/monitoringSystemData/prometheus`** and **`~/monitoringSystemData/grafana`** directories on the host machine, respectively. These directories are mounted as volumes in their respective containers, allowing the data to persist across container restarts.

## **Network**

All services are connected to the **`monitoring`** network. This allows them to communicate with each other using their service names as hostnames.

## **Volumes**

The **`prometheus-data`** and **`grafana-data`** volumes are used to persist data for Prometheus and Grafana, respectively, across container restarts. These volumes are created as local bind mounts on the host system, mapped to the directories specified by the **`device`** property in their respective sections of the **`docker-compose.yml`**
