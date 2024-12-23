# MING Stack Project

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
   git clone https://github.com/gmforde/ming-stack.git
   cd ming-stack
   ```

2. Deploy the stack in Portainer:
   - Log into the Portainer web interface.
   - Navigate to **Stacks** in the menu.
   - Click **+ Add Stack**.
   - Provide a name for the stack (e.g., `MING Stack`).
   - Copy and paste the contents of the `docker-compose.yml` file into the editor.
   - Click **Deploy the stack**.

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

## Help Specific for Container Components

If you encounter issues with any of the components in the MING stack, refer to the following help topics:

### Mosquitto Broker
- Check the logs with:
  ```bash
  docker logs mosquitto
  ```
- Ensure the configuration file `mosquitto.conf` is correctly set up.
- Verify that port 1883 is open and not blocked by a firewall.

### InfluxDB
- Access the logs with:
  ```bash
  docker logs influxdb
  ```
- Ensure the database is accessible at `http://localhost:8086`.
- Verify user credentials and database retention policies.

### Node-Red
- View the logs with:
  ```bash
  docker logs nodered
  ```
- Check the Node-Red editor at `http://localhost:1880` for flow issues.
- Confirm that all required nodes and integrations are installed.

### Grafana
- Check logs with:
  ```bash
  docker logs grafana
  ```
- Ensure dashboards are properly configured and data sources are connected.
- Verify that the Grafana server is accessible at `http://localhost:3000`.

## Environment Variables

Each container in the MING stack can be configured using environment variables. Below are some commonly used variables:

### Mosquitto
- `MOSQUITTO_USER`: MQTT username.
- `MOSQUITTO_PASS`: MQTT password.
- `MOSQUITTO_PORT`: Port for MQTT communication (default: 1883).

### InfluxDB
- `INFLUXDB_ADMIN_USER`: Admin username.
- `INFLUXDB_ADMIN_PASSWORD`: Admin password.
- `INFLUXDB_DB`: Default database name.

### Node-Red
- `NODE_RED_PORT`: Port for Node-Red (default: 1880).

### Grafana
- `GF_SECURITY_ADMIN_USER`: Admin username.
- `GF_SECURITY_ADMIN_PASSWORD`: Admin password.

Update these variables in the `.env` file or directly in the `docker-compose.yml` file.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing
Contributions are welcome! Please submit a pull request or raise an issue for feature requests and bug reports.
