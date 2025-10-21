# Tasks for Installing Metrics Server

## Ordered Task List

- [x] **Add metrics-server Helm release to base kustomization**
  - Add Helm chart reference to `environments/kubernetes/base/kustomization.yaml`
  - Configure values for homelab environment (disable TLS, enable insecure TLS)

- [x] **Create metrics-server values.yaml**
  - Create `environments/kubernetes/base/metrics-server-values.yaml`
  - Set appropriate resource limits and tolerations

- [x] **Update production overlay**
  - Ensure prod overlay includes the base metrics-server configuration
  - Test deployment in prod environment

- [x] **Verify metrics collection**
  - Deploy changes to cluster
  - Check that `kubectl top nodes` and `kubectl top pods` work
  - Confirm dashboard widgets no longer show errors

- [x] **Update documentation**
  - Add metrics-server to project.md external dependencies
  - Document the installation in README if needed