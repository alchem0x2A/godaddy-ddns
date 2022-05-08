# Simple example of kubernetes cronjob with ddns update
## Installation
1. Change the following fields accordingly
    - `secret.yaml`: `GODADDY_API_KEY` and `GODADDY_API_SECRET` as base64-strings of secrets
    - `ddns-cronjob.yaml`: value for env `GODADDY_DOMAIN` as the domain name, e.g. `www.example.com`
    - (Optional) `ddns-cronjob.yaml`: change `schedule` field for the job execution period (example is once per hour)
2. Apply yaml
```bash
cd kubernetes
kubectl apply -n <namespace> -f .
```
3. Check the cronjob ` godaddy-ddns-update` under `namespace` and monitor its log.