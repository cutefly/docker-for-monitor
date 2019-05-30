# docker-for-monitor
influxdb, grafana, telegraf

~~~
docker network create monitoring

docker run --rm \
  -e INFLUXDB_DB=telegraf \
  -e INFLUXDB_ADMIN_ENABLED=true \
  -e INFLUXDB_ADMIN_USER=admin \
  -e INFLUXDB_ADMIN_PASSWORD=supersecretpassword \
  -e INFLUXDB_USER=telegraf \
  -e INFLUXDB_USER_PASSWORD=secretpassword \
  -v /opt/docker-for-monitor/influxdb:/var/lib/influxdb \
  influxdb /init-influxdb.sh

chown 472:472 /opt/docker-for-monitor/grafana

docker-compose up -d
~~~
