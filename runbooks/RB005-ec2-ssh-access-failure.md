# RB005 — EC2 SSH Access Failure

**Severity:** P1
**System:** HostPilot EC2 Instances
**Owner:** SRE / Platform Engineering

## Symptoms
- Connection timed out on port 22
- Permission denied (publickey)

## Diagnosis
1. Test-NetConnection -ComputerName <ip> -Port 22
2. Check EC2 status checks in AWS Console
3. Verify Security Group has port 22 open

## Resolution
- WiFi blocking: switch networks or use EC2 Instance Connect
- Instance unhealthy: Reboot from AWS Console
- Wrong key: ssh -i C:\Users\User\Downloads\hostpilot-sim-key.pem ubuntu@<ip>
- New IP after restart: check AWS Console for current Public IPv4

## Verification
ssh -i ~/.ssh/hostpilot-sim-key.pem ubuntu@<ip>
