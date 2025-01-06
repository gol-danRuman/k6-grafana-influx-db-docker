# docker-k6-grafana-influxdb
Demonstrates how to run load tests with containerised instances of K6, Grafana and InfluxDB.

#### To Run Project
docker-compose up -d influxdb grafana

docker-compose run k6 run /scripts/stress-test.js


Grafana Url
http://localhost:3000/

Influx DB Url 
http://localhost:8888/



#### Dashboards
The dashboard in /dashboards is adapted from the excellent K6 / Grafana dashboard here:
https://grafana.com/grafana/dashboards/2587

There are only two small modifications:
* the data source is configured to use the docker created InfluxDB data source
* the time period is set to now-15m, which I feel is a better view for most tests

#### Scripts
The script here is an example of a low Virtual User (VU) load test of the excellent Star Wars API:
https://swapi.dev/

If you're tinkering with the script, it is just a friendly open source API, be gentle!


## References:

https://www.youtube.com/watch?v=qnPGSRc-BhU&ab_channel=HuzaifaAsif


## Steps:

1. Install Docker Desktop
2. Install Docker Compose
3. Clone https://github.com/Huzaifa-Asif/K6-Local-Testing-With-Grafana-InfluxDB
4. Run `cd K6-Local-Testing-With-Grafana-InfluxDB`
5. Run `docker-compose up -d`
6. Run `docker-compose run k6 run /scripts/stress-test.js`
7. Open Grafana at http://localhost:3000/
8. Open InfluxDB at http://localhost:8888/
9. Run `docker-compose down`
10. Run `docker-compose up -d` to start the containers again



