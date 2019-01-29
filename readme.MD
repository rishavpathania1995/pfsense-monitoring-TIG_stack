# Monitoring pfsense with Telegraf , influxdb and grafana.

### Prerequiste

```
Setup pfsense
Setup Telegraf , influxdb ,and grafana.

```


### Steps

In pfsense install Go to > package manager > available package > install telegraf.

Setup Influx db in docker .
```
docker run -it -p 8086:8086  -e INFLUXDB_DB=pfsense -e INFLUXDB_ADMIN_ENABLED=true -e  INFLUXDB_ADMIN_USER=admin -e  INFLUXDB_ADMIN_PASSWORD=admin influxdb

```

Setup Grafana in docker.

```
docker run -td --name grafana -p 3000:3000 grafana/grafana
```
default user:pass for grafana is admin:admin

In pfsense go to > services > telegraf 
fill up the configuration.

Now ,we will setup grafana ,
Login to grafan dashboad .
Add datasource as influx db and add the required Credentials .
Then go to dashboard and copy / paste the json data in json file in this repo.
