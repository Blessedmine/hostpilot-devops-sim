# RB004 — Kubernetes Pod CrashLoopBackOff

**Severity:** P1
**System:** HostPilot Kubernetes (kind cluster)
**Owner:** SRE / Platform Engineering

## Symptoms
- kubectl get pods shows CrashLoopBackOff

## Diagnosis
1. kubectl describe pod hostpilot-api
2. kubectl logs hostpilot-api -c iis-app --previous

## Resolution
- kubectl delete pod hostpilot-api
- kubectl apply -f kubernetes/hostpilot-sidecar.yaml

## Verification
kubectl get pods
