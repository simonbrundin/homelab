## Context

Dispatcharr will sit between the Xtream IPTV provider and Jellyfin. The homelab repository deploys production applications through Flux-managed HelmReleases and exposes them through the existing Envoy Gateway.

## Goals / Non-Goals

- Goals: deploy a persistent single-instance Dispatcharr service, expose its web UI, and keep provider credentials out of Git.
- Non-Goals: migrate Jellyfin immediately, configure provider credentials automatically, or provide high availability.

## Decisions

- Use the community-maintained TrueCharts OCI chart `oci://oci.trueforge.org/truecharts/dispatcharr` at a pinned chart version.
- Use the chart's AIO mode with embedded PostgreSQL and Redis to keep the initial homelab deployment small.
- Persist `/data` using Longhorn `longhorn-single-replica`; Dispatcharr configuration and database data must survive pod replacement.
- Configure the HTTPRoute separately in the app directory and use the existing `simons-gateway` Gateway.
- Keep Dispatcharr and Jellyfin separate: Jellyfin remains on its existing configuration until Dispatcharr is verified.

## Risks / Trade-offs

- TrueCharts is not the upstream Dispatcharr project and adds an external chart dependency.
- The chart advertises a maximum Kubernetes version of 1.35.0 while the cluster contains 1.36.x workers; render and dry-run validation must pass before reconciliation.
- AIO is single-instance and not highly available.

## Migration Plan

1. Reconcile the Dispatcharr HelmRepository and HelmRelease.
2. Complete initial setup in the Dispatcharr UI and add the Xtream provider.
3. Configure and test M3U/XMLTV output from Dispatcharr.
4. Add a new Jellyfin tuner pointing to Dispatcharr only after successful testing.
5. Keep the existing Jellyfin Xtream source available until migration is confirmed.

## Open Questions

- Whether the chart's advertised Kubernetes maximum is enforced by the chart or only metadata.
- Which Dispatcharr output endpoint and credentials should be used for Jellyfin after the UI setup.
