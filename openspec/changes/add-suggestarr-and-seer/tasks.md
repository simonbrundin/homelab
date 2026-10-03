## 1. Implementation

- [x] 1.1 Skapa Kubernetes-namespace för suggestarr
- [x] 1.2 Skapa suggestarr Deployment + Service + PVC
- [x] 1.3 Skapa suggestarr HTTPRoute
- [x] 1.4 Skapa Jellyseerr Deployment + Service + PVC
- [x] 1.5 Skapa Jellyseerr HTTPRoute
- [x] 1.6 Lägg till tjänster till `environments/prod/kustomization.yaml`
- [x] 1.7 Uppdatera Homepage configMap med suggestarr och jellyseerr
- [x] 1.8 Validera med `kubectl kustomize environments/prod/`

## 2. Verification

- [ ] 2.1 Applicera och verifiera att pods startar
- [ ] 2.2 Verifiera att HTTPRoutes pekar rätt
- [ ] 2.3 Testa webbgränssnitt för båda tjänsterna
