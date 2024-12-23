# MING Manufacturing Tech Stack Project

This repository contains the Docker and Portainer setup for the MING Stack, which includes the following components:

- **Mosquitto Broker**: A lightweight and secure MQTT broker for IoT communication.
- **InfluxDB**: A time-series database optimized for high-performance data storage and retrieval.
- **Node-Red**: A flow-based development tool for visual programming, enabling easy integration of IoT devices and systems.
- **Grafana**: A powerful visualization and analytics platform for monitoring metrics and logs.

## Project Overview
The MING stack provides a comprehensive solution for industrial IoT (IIoT) applications, enabling efficient data collection, processing, and visualization. This setup is managed using Docker and Portainer for simplified deployment and orchestration.

## Features
- **Containerized Architecture**: Each component runs as a separate container, ensuring modularity and ease of management.
- **Portainer Management**: A user-friendly interface to manage Docker containers, images, and networks.
- **Secure Communication**: Support for MQTT over TLS in Mosquitto and secure data storage in InfluxDB.
- **Scalable Visualization**: Grafana dashboards for monitoring and analytics with real-time updates.
- **Easy Integration**: Node-Red enables seamless integration of IoT devices and external APIs.

## Prerequisites
- Docker installed on your host system.
- Portainer set up and accessible via a web browser.
- Adequate system resources to support the MING stack components.

## Installation

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/ming-stack.git
   cd ming-stack
   ```

2. Start the stack using Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Access the services:
   - **Mosquitto**: MQTT broker available on `mqtt://localhost:1883`
   - **InfluxDB**: Web UI available at `http://localhost:8086`
   - **Node-Red**: Accessible at `http://localhost:1880`
   - **Grafana**: Dashboards available at `http://localhost:3000`

## Configuration

- **Mosquitto Broker**: Update the `mosquitto.conf` file to configure MQTT topics, security, and logging.
- **InfluxDB**: Use the `influxdb.conf` file to configure database retention policies and authentication.
- **Node-Red**: Import your custom flows through the Node-Red UI.
- **Grafana**: Set up dashboards and connect to InfluxDB as the data source.

## Default Credentials

### Grafana
- Username: `admin`
- Password: `admin`

### InfluxDB
- Username: `admin`
- Password: `password`

## Ports Used
- Mosquitto: 1883 (MQTT), 8883 (MQTT over TLS)
- InfluxDB: 8086
- Node-Red: 1880
- Grafana: 3000

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing
Contributions are welcome! Please submit a pull request or raise an issue for feature requests and bug reports.

## Support
For any issues or questions, please contact [your-email@example.com](mailto:your-email@example.com).
