FROM grafana/grafana:latest

# Copy your datasource and dashboard configuration into the image
COPY datasources/datasource.yaml /etc/grafana/provisioning/datasources/datasource.yaml
COPY dashboards/dashboard.yaml /etc/grafana/provisioning/dashboards/dashboard.yaml
COPY dashboards/dashboard.json /var/lib/grafana/dashboards/dashboard.json

# Expose the default Grafana port
EXPOSE 3000
