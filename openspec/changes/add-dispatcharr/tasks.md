## 1. Proposal and validation

- [x] 1.1 Confirm upstream installation model and TrueCharts availability.
- [x] 1.2 Check Artifact Hub/TrueCharts metadata and Kubernetes compatibility.
- [x] 1.3 Validate the OpenSpec change.

## 2. GitOps manifests

- [x] 2.1 Add the Dispatcharr namespace and Kustomization resources.
- [x] 2.2 Add the TrueCharts HelmRepository and pinned HelmRelease.
- [x] 2.3 Add persistent storage and resource/security values.
- [x] 2.4 Add the Dispatcharr HTTPRoute.
- [x] 2.5 Include Dispatcharr in the production aggregator.

## 3. Verification

- [x] 3.1 Render the app and production Kustomize manifests.
- [x] 3.2 Run Kubernetes dry-run validation.
- [ ] 3.3 Reconcile Flux and verify the HelmRelease, pod, PVC, Service, and HTTPRoute.
- [ ] 3.4 Perform initial Dispatcharr UI/provider setup without committing credentials.
