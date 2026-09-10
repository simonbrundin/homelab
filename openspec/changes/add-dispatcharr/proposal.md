## Why

Jellyfin's current Xtream plugin is able to authenticate against the IPTV provider, but its EPG handling fails on the provider's large identifiers and some streams are unstable. Dispatcharr will provide an IPTV management layer that can normalize provider data, filter broken channels, and expose M3U/XMLTV feeds to Jellyfin.

## What Changes

- Add Dispatcharr as a production homelab application through the TrueCharts OCI Helm chart in AIO mode.
- Persist Dispatcharr data on a Longhorn-backed PVC.
- Expose the Dispatcharr web interface through an HTTPRoute.
- Keep IPTV provider credentials out of Git; configure them through Dispatcharr after deployment.
- Do not change Jellyfin's current Xtream configuration as part of this change.

## Impact

- Affected capability: new Dispatcharr IPTV management service.
- Affected files: `environments/prod/dispatcharr/` and `environments/prod/kustomization.yaml`.
- A new hostname, `dispatcharr.simonbrundin.com`, will be routed through the existing Envoy gateway.
- Dispatcharr will initially run as a single replica without HA.
