## Day 4 — Traffic Observations

### DNS traffic spike
Generated 50 DNS queries to Pi-hole using a bash loop.
Observed network receive bytes spike in Grafana immediately.
Pi-hole query log confirmed all 50 queries were processed.

### CPU load test
Used stress tool to load CPU for 60 seconds.
Grafana CPU panel showed spike from baseline to elevated usage.
Confirmed monitoring stack detects real time system events.

### Key observation
The monitoring stack detected both events within the 15 second
scrape interval configured in prometheus.yml. This confirms the
pipeline from Node Exporter → Prometheus → Grafana is working
end to end.
