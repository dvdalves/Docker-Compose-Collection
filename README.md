# 🐳 Coleção de Docker Compose

Repositório pessoal com diversos arquivos **docker-compose.yml** prontos para uso.  
Cada serviço pode ser iniciado de forma independente conforme a necessidade.

---

## 📁 Estrutura

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
│      └── jaeger.yml
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
       ├── azurite.yml
```

---

## 🚀 Uso

Entre na pasta do serviço e execute:

```bash
docker compose -f <arquivo>.yml up -d
```

Exemplo:

```bash
cd databases
docker compose -f postgres.yml up -d
```

Para parar e remover:

```bash
docker compose -f postgres.yml down
```

---

## ⚡ Comandos Rápidos

| Ação                      | Comando                                         |
| ------------------------- | ----------------------------------------------- |
| Subir o serviço           | `docker compose -f <arquivo>.yml up -d`         |
| Parar o serviço           | `docker compose -f <arquivo>.yml down`          |
| Parar e remover volumes   | `docker compose -f <arquivo>.yml down -v`       |
| Ver logs                  | `docker compose -f <arquivo>.yml logs -f`       |
| Ver containers ativos     | `docker ps`                                     |
| Ver containers do compose | `docker compose -f <arquivo>.yml ps`            |
| Recriar sem cache         | `docker compose -f <arquivo>.yml up -d --build` |
| Entrar no container       | `docker exec -it <container> bash`              |
| Ver volumes               | `docker volume ls`                              |
| Ver redes                 | `docker network ls`                             |

---

## 🧩 Observações

- Cada serviço é isolado e usa sua própria rede e volume.
- Pode combinar arquivos com `-f` se precisar subir mais de um serviço.
- Personalize variáveis diretamente no `.yml` ou via `.env` local.
