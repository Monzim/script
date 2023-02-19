# Prometheus Configuration

This repository contains a sample Prometheus configuration file (**`prometheus.yml`**) with comments explaining each section of the file.

## **Installation**

To use this configuration file, you will need to have Prometheus installed on your system. You can download and install Prometheus from the **[official Prometheus website](https://prometheus.io/download/)**.

Once Prometheus is installed, copy the **`prometheus.yml`** file to the Prometheus configuration directory (by default, **`/etc/prometheus/`**).

## **Usage**

After copying the configuration file to the Prometheus configuration directory, restart the Prometheus service for the changes to take effect. On a Linux system, you can restart the Prometheus service using the following command:

```bash
sudo systemctl restart prometheus
```

The configuration file includes three scrape configurations, which determine what metrics are collected and from where.

- The **`prometheus`** scrape configuration is for scraping metrics from the Prometheus server itself.
- The **`node_exporter`** scrape configuration is for scraping metrics from the node_exporter.
- The **`cadvisor`** scrape configuration is for scraping metrics from cAdvisor.

Each scrape configuration specifies the endpoint to scrape, and in the case of the Prometheus scrape configuration, overrides the global scrape interval with a shorter interval of 5 seconds.
