# Docker Secrets

## Sample secret

```bash
less mysecret.txt
```

```bash
less docker-compose.yml
```

Deploy stack with secrets from local file

Init swarm if not yet a swarm
```bash
docker swarm init
```

```bash
docker stack deploy -c docker-compose.yml secret
```

```bash
docker service logs -f secret_test
```

## existing secret

```bash
echo "some other secret" | docker secret create manual_secret -
```

```bash
docker stack deploy -c external-compose.yml external_secret
```

```bash
docker service logs -f external_secret_test
```

## Clean up

```bash
docker stack rm secret
```

```bash
docker stack rm external_secret
```

```
docker swarm leave --force
```
