### 1 - Create a datasource variable.
http://localhost:9090/api/v1/query?     -> To get some 4XX errors.


### 2 - Create a code variable.
query: group (prometheus_http_requests_total) by (code) <br/>
regex: {code="([^"]+)"\}|

### 3 - Multi-query panel

### 4 - Grafana API
- Add Prometheus datasource:<br/>curl -X POST 'http://localhost:3001/api/datasources' -H 'Content-Type: application/json;charset=UTF-8' --user 'admin:admin' --data-binary '{"name":"prometheus","type":"prometheus","url":"http://prometheus:9090/","access":"proxy","isDefault":true}'
- Add HTTP dashboard:<br/>curl -X POST --insecure -H "Content-Type: application/json" -d "{\"dashboard\":$(cat dashboards/http.json)}" --location http://localhost:3001/api/dashboards/import --user 'admin:admin'
- Add clock dashboard:<br/>curl -X POST --insecure -H "Content-Type: application/json" -d "{\"dashboard\":$(cat dashboards/clock.json)}" --location http://localhost:3001/api/dashboards/import --user 'admin:admin'
- Add clock plugin:<br/>curl -X POST --insecure -H 'Content-Type: application/json;charset=UTF-8' --location http://localhost:3001/api/plugins/grafana-clock-panel/install --user 'admin:admin' --data-binary '{"name":"clock","type":"panel","id":"grafana-clock-panel","enabled":true,"pinned":false,"info":{"author":{"name":"Grafana Labs","url":"https://grafana.com"},"description":"Shows","links":null,"build":{},"screenshots":null,"version":"","updated":""},"dependencies":{"grafanaDependency":"","grafanaVersion":"*","plugins":[]},"hasUpdate":false,"defaultNavUrl":"/plugins/clock/"}'

### 5 - docker container image

### 6 - Grafana Cloud

Grafana Agent<br/>
Simplify deployment and management of your telemetry data with the Grafana Agent, a lightweight collector for sending metrics, logs, and traces to Grafana Cloud.

### 7 - AMG - Amazon Managed Grafana
- Users
- AWS integration
- Billing