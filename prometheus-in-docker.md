

```
version: '3.9'
services:
  prometheus:
    container_name: prometheus
    image: prom/prometheus
    ports:
      - 9090:9090
    volumes:
      - prometheus_config:/etc/prometheus
    networks:
      - prometheus_network
    restart: unless-stopped

volumes:
  prometheus_config:

networks:
  prometheus_network:
    driver: bridge
```
