# Tasks for Disabling Metrics Server Dependency

## Ordered Task List

- [x] **Remove metrics-server from base kustomization**
  - Remove Helm chart reference from `environments/kubernetes/base/kustomization.yaml`
  - Remove metrics-server-values.yaml file

- [x] **Update homepage config map**
  - Modify `environments/kubernetes/overlays/prod/homepage/configmap.yaml`
  - Disable CPU/memory display in kubernetes cluster and nodes widgets
  - Configure resources widget to not require metrics

- [x] **Verify dashboard works without metrics**
  - Test kustomization build
  - Ensure homepage config is valid
  - Confirm widgets display without errors