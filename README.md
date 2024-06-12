# VLLM + Open-WebUI Deployment Guide

This repository contains the necessary configuration to deploy a high-performance language model inference service using [VLLM](https://github.com/vllm-project/vllm) and a user-friendly web interface with [Open-WebUI](https://github.com/open-webui/open-webui). The setup is designed to leverage NVIDIA GPUs for efficient computation and provide an interactive experience through a web-based UI.

## Overview

- **VLLM Service (`vllm-openai`)**: A Dockerized service based on the VLLM framework, which is optimized for running large transformer models like the ones from Hugging Face. It serves as the backend for generating text completions and responses.
  
- **Open-WebUI**: A web frontend that communicates with the VLLM service to provide a seamless user interaction experience. Users can input prompts and receive model-generated outputs through this intuitive interface.

## Prerequisites

1. **Docker**: Ensure Docker is installed on your system. You can download it from the [official Docker website](https://www.docker.com/get-started).
2. **Docker Compose**: Docker Compose is required for managing multi-container Docker applications. Install or update it following the [official guide](https://docs.docker.com/compose/install/).
3. **NVIDIA GPU**: A system equipped with one or more NVIDIA GPUs and the appropriate drivers installed.
4. **CUDA & cuDNN**: Ensure your system has CUDA and cuDNN compatible with the specified VLLM image version.

## Deployment Steps

### 1. Clone the Repository

```bash
git clone https://github.com/GeeseDream/vllm-openwebui
cd vllm-openwebui
```

### 2. Start the Services

Run the following command to start both services defined in `docker-compose.yml`:

```bash
docker-compose up -d
```

This will:
- Deploy the VLLM service with GPU resources allocated.
- Start the Open-WebUI, which will connect to the VLLM service internally.

### 4. Accessing Open-WebUI

Open your browser and navigate to `http://localhost:3000` (or `${OPEN_WEBUI_PORT}` as defined in `.env`). You should see the Open-WebUI interface ready for interaction.

## Note on Security

- **API Key**: Ensure you replace the placeholder `OPENAI_API_KEY` with a secure value. Never expose your actual keys in public repositories or share them insecurely.
- **Data Privacy**: Remember that any data processed through this setup will be subject to the privacy policies and security practices implemented by VLLM and Open-WebUI.

## Troubleshooting

For any issues during deployment, refer to the logs using `docker logs <container_name>` or consult the respective project documentations for [VLLM](https://github.com/vllm-project/vllm) and [Open-WebUI](https://github.com/open-webui/open-webui).

Enjoy exploring the capabilities of advanced language models through this efficient and user-friendly setup!