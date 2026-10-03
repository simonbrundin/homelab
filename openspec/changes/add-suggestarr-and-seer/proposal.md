## Why

Homelab-användare behöver ett sätt att automatiskt upptäcka nytt innehåll baserat på vad de tittar på, samt ett användarvänligt gränssnitt för att begära media. SuggestArr analyserar Jellyfin-historik via TMDb för att rekommendera nytt innehåll och skickar begäanden vidare till Jellyseerr (Overseerr-klon). Jellyseerr ger ett webbgränssnitt för att hantera mediabegäran.

## What Changes

- Lägger till **SuggestArr** — automatisk innehållsrekommendation baserat på Jellyfin-tittarhistorik
- Lägger till **Jellyseerr** — webbgränssnitt för mediabegäran integrerat med Jellyfin
- Exponerar båda tjänsterna via HTTPRoute/Envoy Gateway
- Uppdaterar Homepage-configMap med nya tjänster

## Impact

- Affected specs: `homelab-media-automation` (ny)
- Affected code: `environments/prod/suggestarr/`, `environments/prod/jellyseerr/`, `environments/prod/kustomization.yaml`, `environments/kubernetes/overlays/prod/homepage/configmap.yaml`
- Nytt Docker-image för Jellyseerr (hotio)
- Ingen befintlig funktionalitet påverkas
