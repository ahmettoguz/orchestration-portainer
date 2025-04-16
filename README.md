<h1 id="top" align="center">🚢 v1.2.0 🚢</h1>

<br>

## 🔍 Table of Contents

- [Features](#features)
- [System Startup](#system-startup)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Network Compatibility:** Uses shared Docker network to work with other services.
- **Persistent Data:** Binds the data directory from the host machine to the container, ensuring persistent data storage even with container restarts.
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

- Run Container.

```
docker stop                                   orchestration-portainer-c
docker rm                                     orchestration-portainer-c
docker compose -p orchestration up --build -d portainer
docker logs -f                                orchestration-portainer-c
```

<br/>

### [🔝](#top)
