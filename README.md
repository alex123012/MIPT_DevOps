# MIPT_DevOps

## Postgres

Запустить postgres:

```bash
podman build -t postgres:mipt -f Dockerfile.postgres
podman run --rm -p 5432:5432 postgres:mipt
```

Проверить задание:

```bash
psql -h 127.0.0.1 -U test test
```

```text
psql (17.0, server 16.4)
Type "help" for help.

test=#
```

## Nginx

Запустить postgres:

```bash
podman build -t nginx:mipt -f Dockerfile.nginx
podman run --rm -p 8080:80 nginx:mipt
```

Проверить задани:

```bash
curl 127.0.0.1:8080
```

```text
{"status": "forbidden"}
```

```bash
curl 127.0.0.1:8080 -XPOST
```

```text
{"status": "ok"}
```
