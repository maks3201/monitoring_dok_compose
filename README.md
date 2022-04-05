# monitoring_dok_compose

There is docker-compose file for monitoring. (prometheus, grafana, node-exporter, loki, promtail)
To change config file in promtail, you need to execute:
1. docker exec -it <container with promtail> /bin/bash
2. and change file /etc/promtail/config.yml
3. exit
4. and then docker-compose restart

To add node-exporter job in prometheus:
1. add 
 '- job_name: "node-exporter"
    static_configs:
      - targets: ["node-exporter:9100"]'
in /var/lib/docker/volumes/monitoring_dok_compose_prom-configs/_data/prometheus.yml
2. docker-compose restart

Also you can do import 'node-exporter.json.txt' in grafana as dashboard's file configuration. 
