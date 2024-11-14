# avs-metrics-reporting
Example using Prometheus remote write to move metrics from an AVS istance to a remote prometheus server.

## Usage

Place a valid Aerospike features.conf file in the "volumes" directory. Then run `docker compose up`.
Metrics will be available through grafana at localhost:3004 with login admin, admin.

## Architecture

This is a proof of concept for pushing AVS metrics to a remote central Prometheus and Grafana.
The docker compose starts up side-prometheus which scrapes metrics from AVS. This then uses remote write to push the metrics to central-prometheus
which is then used by Grafana to display the metrics. In a real world deployment, the central-prometheus and Grafana instances would already be deployed.

## Next steps

Configure TLS and test with a deployed central Prometheus server.

