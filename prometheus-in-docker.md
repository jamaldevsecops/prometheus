#### 1. Go to the directory where the dockerc-compose.yml file will be kept. 
```
cd /path_to_desired_dir/
mkdir prometheus && cd prometheus
```
#### 2. Copy the following contents and past them in the docker-compose file. 
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
#### 3. Run the docker-compose.yml file. 
```
docker-compose up -d
```
#### 4. Run the following URL on the browser. 
```
http://your_ip_address:9090
```
