## Why
The homelab dashboards (Dashy/Homepage) are failing to display resource metrics with error: "Error getting metrics, ensure you have metrics-server installed". This prevents users from monitoring cluster resource usage and breaks dashboard functionality.

## What Changes
- Deploy metrics-server Helm chart to Kubernetes cluster
- Configure metrics-server for homelab environment (disable TLS verification)
- Update base kustomization to include metrics-server

## Impact
- Affected specs: metrics-server (new capability)
- Affected code: environments/kubernetes/base/kustomization.yaml, new values file