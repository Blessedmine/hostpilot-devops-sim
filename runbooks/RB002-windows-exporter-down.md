# RB002 — Windows Exporter Not Scraping

**Severity:** P2
**System:** HostPilot Windows VM
**Owner:** SRE / Platform Engineering

## Symptoms
- windows-iis target shows DOWN in Prometheus
- No Windows metrics in Grafana

## Diagnosis
1. curl http://172.31.8.142:9182/metrics
2. RDP into Windows VM, check Services for windows_exporter

## Resolution
- PowerShell: Start-Service windows_exporter
- Firewall: New-NetFirewallRule -LocalPort 9182 -Action Allow

## Verification
curl http://172.31.8.142:9182/metrics | head -20
