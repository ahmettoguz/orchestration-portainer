<h1 id="top" align="center">Core Portainer</h1>

<br>

<div align="center">
    <img height=200 src="assets/banner/banner.png">
</div>

<br>

## 🔍 Table of Contents

- [About Project](#intro)
- [Dashboard](#dashboard)
- [Technologies](#technologies)
- [Features](#features)
- [Releases](#releases)
- [System Startup](#system-startup)
- [Contributors](#contributors)

<br/>

<h2 id="intro">📌 About Project</h2>

This project aims to simplify the use of Portainer with pre-configured settings, including persistent bind mount data and Docker Compose for container management.

<br/>

<h2 id="dashboard">🐳 Dashboard</h2>

<div align="center">
    <img width=800 src="assets/portainer-dashboard/portainer-dashboard.png">
</div>

<br/>

<h2 id="technologies">☄️ Technologies</h2>

&nbsp; [![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

&nbsp; [![Portainer](https://img.shields.io/badge/Portainer-13BEF9?style=for-the-badge&logo=portainer&logoColor=white)](https://www.portainer.io/)

<br/>

<h2 id="features">🔥 Features</h2>

- **Docker Containerization:** The application is containerized using Docker to ensure consistent deployment, scalability, and isolation across different environments.
- **Persistent Data:** Utilizes bind mounts to persist data on the host machine, preventing data loss during container restarts.
- **Docker Compose Deployment:** Simplifies deployment with Docker Compose configuration, enabling easy setup and service orchestration without complex commands.
- **Predefined Admin Credentials:** Allows the use of a predefined admin password stored in a configuration file.

<br/>

<h2 id="releases">🚢 Releases</h2>

&nbsp; [![.](https://img.shields.io/badge/1.2.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/core-portainer/tree/v1.2.0)

&nbsp; [![.](https://img.shields.io/badge/1.1.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/core-portainer/tree/v1.1.0)

&nbsp; [![.](https://img.shields.io/badge/1.0.0-233838?style=flat&label=version&labelColor=111727&color=1181A1)](https://github.com/ahmettoguz/core-portainer/tree/v1.0.0)

<br/>

<h2 id="system-startup">🚀 System Startup</h2>

- Create a new directory named `core`.

```
mkdir core
cd core
```

- Clone project.

```
git clone https://github.com/ahmettoguz/core-portainer
```

- Generate secure password.

```
docker run --rm alpine sh -c "apk add --no-cache openssl && openssl rand -base64 32"
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

<h2 id="contributors">👥 Contributors</h2>

<a href="https://github.com/ahmettoguz" target="_blank"><img width=60 height=60 src="https://avatars.githubusercontent.com/u/101711642?v=4"></a>

### [🔝](#top)
