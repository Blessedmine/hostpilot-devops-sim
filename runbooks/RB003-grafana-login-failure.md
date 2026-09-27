# RB003 — Grafana Login Failure

**Severity:** P2
**System:** HostPilot Monitoring Stack
**Owner:** SRE / Platform Engineering

## Symptoms
- Cannot log in at http://3.219.237.200:3000
- Invalid username or password error

## Diagnosis
1. docker compose ps grafana
2. docker compose logs --tail=50 grafana

## Resolution
- Reset password: docker compose exec grafana grafana-cli admin reset-admin-password hostpilot123
- Restart: docker compose restart grafana

## Verification
Open http://3.219.237.200:3000 — login: admin / hostpilot123
