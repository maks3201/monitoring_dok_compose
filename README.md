# monitoring_dok_compose
Here docker-compose file for monitoring. (prometheus, grafana, node-exporter, loki, promtail)
To change config file in promtail, you need to execute:
docker exec -it <container with promtail> /bin/bash
and change file /etc/promtail/config.yml
exit
and then docker-compose restart
