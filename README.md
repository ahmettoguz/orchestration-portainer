<h1 id="top" align="center">🚢 v1.0.0 🚢</h1>

<br>

## 🔍 Table of Contents

- [Features](#features)
- [System Startup](#system-startup)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Persistent Data:** Utilizes bind mounts to persist data on the host machine, preventing data loss during container restarts.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Predefined Admin Credentials:** Allows the use of a predefined admin password stored in a configuration file.

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `core`.

```
git clone https://github.com/ahmettoguz/core-portainer
```

- Create `portainer_password` file based on the `portainer_password.example` file and modify it to set secure initial admin password.

```
cp portainer_password.example portainer_password
```

- Create `network-core` network if not exists.

```
docker network create network-core
```

- Run Container.

```
docker stop                           core-portainer-c
docker rm                             core-portainer-c
docker compose -p core up --build -d  portainer
docker logs -f                        core-portainer-c
```

<br/>

### [🔝](#top)
