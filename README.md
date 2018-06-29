# Performance Monitor

Full featured Performance Monitor for your web application.

## Start containers
`docker-compose -p grafana up -d`

#### What's next
- [x] Configure docker with InfluxDB & Grafana 
- [ ] [Jest](https://github.com/facebook/jest) + [Puppeteer](https://github.com/GoogleChrome/puppeteer)
- [ ] Add loading time tests examples
- [ ] Add FPS tests examples
- [ ] Add info about time for painting/layouting/scripting for unit tests.
- [ ] Add [jest-allure](https://github.com/zaqqaz/jest-allure) for unit tests reporting


## Grafana
http://localhost:3000

## Features
* Grafana without authentication for user with admin's rights 
* InfluxDB database `js_performance` configured as default data source for Grafana
* InfluxDB database `telegraf` configured as data source for Grafana
* Grafana dashboards are auto-imported from project directory `grafana/dashboards`
* Grafana pre-loaded with dashboard _Docker Metrics per container_ (https://grafana.com/dashboards/3056)
* Telegraf with configuration file in project `telegraf/telegraf.conf`
* Telegraf with Docker stats reading plug-in for local Docker host (for Mac and Linux)
* Telegraf with metrics sending to InfluxDB
* Grafana plug-in _Pie Chart panel_ installed 

## Useful commands
### InfluxDB
Connect to InfluxDB shell:   
`docker run --rm --network=grafana_default --link=grafana_influxdb_1 -it influxdb:1.5.2 influx --host influxdb`
