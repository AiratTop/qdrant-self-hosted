# AGENTS.md

## Purpose
Public self-hosted deployment template for Qdrant vector database.

## Repository Role
- Category: `*-self-hosted` (public GitHub repository).
- Related local stack: `../qdrant-docker`.
- Main entrypoint: `docker-compose.yml`.

## Stack Summary
- Service: `qdrant`.
- Exposed port: `6333`.
- External network: `shared_network`.
- Uses external Docker volume: `qdrant-data`.

## Data and Config
- Vector storage mount: `qdrant-data:/qdrant/storage`.
- API key and telemetry settings are configured via environment variables.

## Operations
- Create external volume helper: `./create-docker-volume.sh`.
- Restart stack: `./restart-docker.sh`.
- Update images and restart: `./update-docker.sh`.

## AI Working Notes
- Keep `QDRANT_API_KEY` in `.env`.
- Do not replace `qdrant-data` with bind mount without migration planning.
- Keep telemetry disabled unless explicit consent to enable diagnostics.
