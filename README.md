# Boilerplate ROS 2 Jazzy com Docker

Este projeto oferece um ambiente básico para desenvolver com o ROS 2 Jazzy utilizando Docker e Docker Compose.

## Estrutura

- `docker-compose.yml`: define o container baseado em `osrf/ros:jazzy-desktop-full`.
- `workspace/`: pasta montada dentro do container em tempo real (`/home/ros/ws`) para receber os pacotes e builds do ROS.

## Como usar

1. **Subir o container em modo idle**
   ```bash
   docker compose up -d
   ```

2. **Conectar-se ao ambiente**
   ```bash
   docker compose exec ros bash
   ```

3. **Ativar o ambiente do ROS 2 dentro do shell**
   ```bash
   source /opt/ros/jazzy/setup.bash
   ```

4. **Organizar e buildar seu workspace**
   ```bash
   mkdir -p src    # dentro de /home/ros/ws
   colcon build
   ```

Os pacotes e artefatos que você criar dentro de `/home/ros/ws` ficarão sincronizados em tempo real com a pasta `workspace/` do host.

## Encerrar

Para parar o container:
```bash
docker compose down
```
