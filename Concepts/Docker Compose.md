#domain/homelab

# Docker Compose

A tool for defining and running multi-container **[[Docker]]** applications from a single YAML file (`docker-compose.yml`), instead of typing out a long `docker run` command for every service. Each service, its image, ports, volumes, environment variables, and dependencies on other services are declared once, then the whole stack starts or stops together.

```yaml
services:
  app:
    image: myapp:latest
    ports:
      - "8080:80"
    volumes:
      - app_data:/data
    restart: unless-stopped

volumes:
  app_data:
```

```bash
docker compose up -d      # start the stack in the background
docker compose down       # stop and remove it
docker compose pull       # fetch newer images
docker compose logs -f    # follow logs across all services
```

This is the format almost every self-hosted app's install instructions ship in, and it's how most homelab stacks (media servers, monitoring, infrastructure) are actually deployed and updated.

### Related
[[Docker]] [[Self-Hosted Service Stack]] [[Container]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
