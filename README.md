# Dockerized Prometheus Node Exporter

This repository contains a Docker Compose configuration for running Prometheus and Node Exporter. Prometheus is a popular open-source monitoring and alerting toolkit, and Node Exporter is a Prometheus exporter for hardware and OS metrics.

## Prerequisites

Before you get started, make sure you have Docker and Docker Compose installed on your system.

- [Docker Installation](https://docs.docker.com/get-docker/)
- [Docker Compose Installation](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

   ```shell
   git clone https://github.com/dennypradipta/dockerized-prometheus-node-exporter
   cd dockerized-prometheus-node-exporter
   ```

2. Place your Prometheus configuration file (`prometheus/prometheus.yml`) in the `prometheus` directory. Customize the configuration to suit your monitoring needs.

3. Start the Prometheus and Node Exporter services using Docker Compose:

   ```shell
   docker-compose up -d
   ```

   The `-d` flag runs the containers in the background.

4. Access Prometheus web interface in your browser at http://localhost:9090 to explore metrics and configure alerting rules. The default credentials is `admin` with the password `admin`. You can change it in the `web.yml` file in the `prometheus` directory.

5. Node Exporter metrics can be accessed at http://localhost:9100/metrics, and Prometheus will automatically scrape these metrics.

## Configuration

- `docker-compose.yml`: Defines the services and their configurations, including port mappings, volume mounts, and restart policies.

- `prometheus/prometheus.yml`: The configuration file for Prometheus. Customize this file to define targets and alerting rules based on your specific needs.

## Container Lifecycle

Both the Prometheus and Node Exporter containers are set to restart unless explicitly stopped using the `unless-stopped` restart policy. This ensures that the containers persistently run, even after system reboots.

## Notes

- Make sure to review and adapt the Prometheus configuration to your monitoring requirements. The provided configuration is a minimal starting point.

- It's recommended to secure your Prometheus setup when deploying it in production environments, as the default setup may not provide adequate security.

## License

This repository is provided under the MIT-0 License. See the [LICENSE](LICENSE) file for details.

Feel free to contribute, report issues, or provide feedback to enhance this configuration.
