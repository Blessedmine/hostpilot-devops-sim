# RB001 — Prometheus Service Down

**Severity:** P1
**System:** HostPilot Monitoring Stack
**Owner:** SRE / Platform Engineering

## Symptoms
- Grafana dashboards show "No Data"
- Port 9090 not responding

## Diagnosis
1. docker compose ps prometheus
2. docker compose logs --tail=50 prometheus
3. curl http://localhost:9090/-/healthy

## Resolution
- Restart: docker compose restart prometheus
- Config error: curl -X POST http://localhost:9090/-/reload

## Verification
curl http://localhost:9090/-/healthy
