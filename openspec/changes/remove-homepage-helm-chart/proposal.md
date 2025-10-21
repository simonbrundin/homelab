## Why
The current Homepage deployment uses a Helm chart, but the user prefers to use direct Kubernetes manifests from the official Homepage documentation for better control, transparency, and to avoid Helm dependencies.

## What Changes
- Remove the Helm chart values.yaml file from the homepage overlay
- Replace Helm-based deployment with direct Kubernetes manifests (ServiceAccount, Secret, ConfigMap, ClusterRole, ClusterRoleBinding, Service, Deployment, Ingress)
- Update kustomization.yaml to reference the new manifests instead of Helm

## Impact
- Affected specs: homepage (new capability)
- Affected code: environments/kubernetes/overlays/prod/homepage/
- No functional changes to the Homepage service itself, only the deployment method