# 🐳 Docker Compose Collection

Personal repository with various **docker-compose.yml** files ready for use.  
Each service can be started independently as needed.

---

## 📁 Structure

```tree
docker-compose-collection/
├── databases/
│      ├── sqlserver.yml
│      ├── postgres.yml
│      ├── mongodb.yml
│      └── redis.yml
├── messaging/
│      ├── rabbitmq.yml
│      ├── kafka.yml
│      └── nats.yml
├── observability/
│      ├── prometheus-grafana.yml
│      ├── loki.yml
│      ├── jaeger.yml
├── devtools/
│      ├── mailhog.yml
│      ├── keycloak.yml
│      ├── portainer.yml
│      └── adminer.yml
├── ci-cd/
│      ├── jenkins.yml
│      ├── gitlab.yml
│      └── sonarqube.yml
└── storage/
       ├── minio.yml
       └── azurite.yml
```

---

## 🚀 Usage

Go to the service folder and run:

```bash
docker compose -f <filename>.yml up -d
```

Example:

```bash
cd databases
docker compose -f postgres.yml up -d
```

To stop and remove:

```bash
docker compose -f postgres.yml down
```

---

## ⚡ Quick Commands

| Action                       | Command                                         |
| ---------------------------- | ----------------------------------------------- |
| Start the service            | `docker compose -f <filename>.yml up -d`        |
| Stop the service             | `docker compose -f <filename>.yml down`         |
| Stop and remove volumes      | `docker compose -f <filename>.yml down -v`      |
| View logs                    | `docker compose -f <filename>.yml logs -f`      |
| View active containers       | `docker ps`                                     |
| View compose containers      | `docker compose -f <filename>.yml ps`           |
| Recreate without cache       | `docker compose -f <filename>.yml up -d --build`|
| Enter the container          | `docker exec -it <container> bash`              |
| View volumes                 | `docker volume ls`                              |
| View networks                | `docker network ls`                             |

---

## 🧩 Notes

- Each service is isolated and uses its own network and volume.
- You can combine files with `-f` if you need to start more than one service. 
- Customize variables directly in the `.yml` or via local `.env` file.