## Why
The user wants to disable metrics-server and configure the dashboard to work without it, avoiding the dependency on metrics collection for basic dashboard functionality.

## What Changes
- Remove metrics-server Helm chart from base kustomization
- Modify homepage config map to disable CPU/memory metrics in kubernetes widgets
- Configure widgets to work without metrics-server dependency

## Impact
- Affected specs: homepage dashboard configuration
- Affected code: environments/kubernetes/base/kustomization.yaml, environments/kubernetes/overlays/prod/homepage/configmap.yaml