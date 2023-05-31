# Docker Compose MariaDB

Docker image base `bitnami/mariadb` [link](https://hub.docker.com/r/bitnami/mariadb)

## Make sure docker network exist:

```bash
docker network create proxy
docker network create secure
```

## Makefile commands for run the code

```bash
make help
```

First of all:

-   Init setup env: `make init`
-   Init docker compose env: `make compose-init`

## Web environment variables

You could custom environment of setup database to development or production on `.make/.env`:

```bash
# Development
DOCKER_PROJECT_DEV=true
```

Or

```bash
# Production
DOCKER_PROJECT_DEV=false
```

📖 Docker compose MariaDB config of `Bitnami MariaDB` [link](https://hub.docker.com/r/bitnami/mariadb)

## Troubleshoot Persisting your database

Error: `mkdir: cannot create directory '/bitnami/mariadb/data': Permission denied`

Now chown this directory to `1001:1001` since the image is using UID `1001` as the user running the command:

```bash
sudo chown -R 1001:1001 [.data/development_db]
```

Or

```bash
sudo chown -R 1001:1001 [.data/master_db]
```

## License

MIT / BSD

## Author Information

This Code was created in 2023 by [Asapdotid](https://github.com/asapdotid).
