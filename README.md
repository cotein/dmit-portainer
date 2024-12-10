# Portainer.io

Portainer.io is a lightweight management UI that allows you to easily manage your Docker environments. It provides a simple and easy-to-use interface for managing Docker containers, images, networks, and volumes.

## Getting Started

This project uses Docker Compose to set up and run Portainer. The `docker-compose.yml` file provided in this repository will help you get started quickly.

### Prerequisites

- Docker
- Docker Compose

### Installation

1. Clone this repository to your local machine.
2. Navigate to the directory containing the `docker-compose.yml` file.
3. Run the following command to start Portainer:

    ```sh
    docker-compose up -d
    ```

4. Open your web browser and go to `http://localhost:9000` to access the Portainer UI.

### Configuration

The `docker-compose.yml` file is configured to use the Portainer Community Edition (CE) version 2.11.0. It maps the following ports:

- `9000:9000` - Portainer UI
- `8000:8000` - Edge agent

Volumes are used to persist Portainer data and to allow Portainer to communicate with the Docker daemon:

- `./volumes/portainer_data:/data` - Persists Portainer data
- `/var/run/docker.sock:/var/run/docker.sock` - Allows Portainer to communicate with the Docker daemon

### Networks

The `docker-compose.yml` file defines two networks:

- `portainer` - A bridge network created by Docker Compose.
- `dmit_network` - An external network that must be created before running the `docker-compose up` command.

### Restart Policy

The `restart` policy is set to `always`, which ensures that the Portainer container will always restart if it stops or if the Docker daemon is restarted.

## Learn More

For more information about Portainer, visit the [official website](https://www.portainer.io/).
 