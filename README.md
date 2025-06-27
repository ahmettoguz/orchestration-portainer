<h1 id="top" align="center">Portainer <br/> 🚢 v1.4.0 🚢</h1>

<br>

<div align="center">
    <img height=200 src="assets/banner/banner.png">
</div>

<br>

## 🔍 Table of Contents

- [Features](#features)
- [System Startup](#system-startup)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Network Compatibility:** Uses shared Docker network to work with other services.
- **Persistent Data:** Utilizes a named Docker volume to ensure persistent storage of application data, allowing data to persist across container restarts, rebuilds, and removals.
- **.env Configuration:** All environment variables are easily configurable using the `.env` file, simplifying configuration management.
- **Predefined Admin Credentials:** Allows the use of a predefined admin password stored in a configuration file.

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `orchestration`.

```
mkdir orchestration
cd orchestration
```

- Clone project.

```
git clone https://github.com/ahmettoguz/orchestration-portainer
```

- Create `.env` file based on the `.env.example` file with credentails.

```
cp .env.example .env
```

- Generate secure password.

```
docker run --rm alpine sh -c "apk add --no-cache openssl && openssl rand -base64 32"
```

- Create `portainer_password` file based on the `portainer_password.example` file and modify it to set secure initial admin password.

```
cp portainer_password.example portainer_password
```

- Create `network-orchestration` network if not exists.

```
docker network create network-orchestration
```

- Manage Container.

```
docker stop                           orchestration-portainer-c
docker rm                             orchestration-portainer-c
docker volume rm                      volume-portainer
docker compose -p orchestration up -d service-portainer
docker logs -f                        orchestration-portainer-c
```

<br/>

### [🔝](#top)
