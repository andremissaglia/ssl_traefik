# SSL Traefik
## Default environment for setting up SSL protocol


To attach a container to the proxy, put in the applications's `docker-compose.yml`

```yaml
services:
  backend:
    labels:
      - "traefik.backend=backend_name"
      - "traefik.frontend.rule=Host:domain.com"
    networks:
      - webgateway

networks:
  webgateway:
    external: true

```

Network `webgateway` has to be previously created:

```
docker network create webgateway
```
