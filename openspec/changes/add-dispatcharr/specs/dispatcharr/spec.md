## ADDED Requirements

### Requirement: Persistent Dispatcharr deployment

The homelab SHALL deploy Dispatcharr through a pinned Flux HelmRelease using the TrueCharts OCI chart, with persistent storage for the application data directory.

#### Scenario: Pod replacement preserves configuration

- **WHEN** the Dispatcharr pod is recreated
- **THEN** its configuration and embedded database data remain available from the Longhorn-backed persistent volume

### Requirement: Dispatcharr web access

The homelab SHALL expose the Dispatcharr web interface through the existing Envoy Gateway at `dispatcharr.simonbrundin.com`.

#### Scenario: User opens Dispatcharr

- **WHEN** a user requests `https://dispatcharr.simonbrundin.com`
- **THEN** the request is routed to the Dispatcharr service on port 9191

### Requirement: Provider credentials remain out of Git

The deployment SHALL not store Xtream provider credentials in the homelab repository.

#### Scenario: Initial provider setup

- **WHEN** Dispatcharr is first configured
- **THEN** the provider credentials are entered through the Dispatcharr UI or another runtime secret mechanism rather than committed to Git
