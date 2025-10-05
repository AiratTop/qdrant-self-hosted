# Qdrant Self-Hosted with Docker

This repository provides a `docker compose` setup to run a self-hosted [Qdrant](https://qdrant.tech/) vector database instance.

It is configured to connect to a shared Docker network, allowing easy integration with other services like [n8n](https://github.com/AiratTop/n8n-self-hosted).

## Features

-   Uses the official Qdrant Docker image.
-   Data is persisted in a local volume.
-   Pre-configured for a shared network.
-   Includes scripts for easy management.
-   Telemetry is disabled by default.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AiratTop/qdrant-self-hosted.git
    cd qdrant-self-hosted
    ```

2.  **Create the shared network:**
    If you haven't already, create the shared Docker network:
    ```bash
    docker network create shared_network
    ```

3.  **Configure environment variables:**
    Open the `.env` file and add your Qdrant API key. You can generate a random secure key.
    ```
    QDRANT_API_KEY=your-secret-api-key
    ```

4.  **Start the service:**
    ```bash
    docker compose up -d
    ```

## Usage

-   **Start:** `docker compose up -d`
-   **Restart:** `./restart-docker.sh`
-   **Update:** `./update-docker.sh` (Pulls the latest Docker image and restarts)

## Connecting with n8n

This setup is designed to work with the [n8n-self-hosted](https://github.com/AiratTop/n8n-self-hosted) configuration. Since both services are on the `shared_network`, you can connect to Qdrant from n8n using `http://qdrant:6333` as the host.

## See Also

Check out other self-hosted solutions:

-   [postgresql-self-hosted](https://github.com/AiratTop/postgresql-self-hosted)
-   [mysql-self-hosted](https://github.com/AiratTop/mysql-self-hosted)
-   [clickhouse-self-hosted](https://github.com/AiratTop/clickhouse-self-hosted)
-   [qdrant-self-hosted](https://github.com/AiratTop/qdrant-self-hosted)
-   [redis-self-hosted](https://github.com/AiratTop/redis-self-hosted)
-   [n8n-self-hosted](https://github.com/AiratTop/n8n-self-hosted)
-   [caddy-self-hosted](https://github.com/AiratTop/caddy-self-hosted)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**Airat Halitov**

- Website: [airat.top](https://airat.top)
- GitHub: [@AiratTop](https://github.com/AiratTop)
- Repository: [qdrant-self-hosted](https://github.com/AiratTop/qdrant-self-hosted)
