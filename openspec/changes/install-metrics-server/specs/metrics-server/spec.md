## ADDED Requirements

### Requirement: Metrics Server Deployment
The system SHALL deploy metrics-server to enable resource metrics collection in the Kubernetes cluster.

#### Scenario: Metrics Collection Enabled
- **WHEN** metrics-server is deployed via Helm
- **THEN** kubectl top commands work
- **AND** dashboard widgets can display CPU/memory usage

### Requirement: Homelab Configuration
The metrics-server SHALL be configured for homelab environments with insecure TLS settings.

#### Scenario: Local Cluster Compatibility
- **WHEN** metrics-server is configured with insecure TLS
- **THEN** it works with local Kubernetes clusters
- **AND** doesn't require external certificate management

### Requirement: Dashboard Integration
The dashboards SHALL successfully retrieve metrics when metrics-server is available.

#### Scenario: Widget Error Resolution
- **WHEN** metrics-server is deployed
- **THEN** dashboard widgets requesting metrics succeed
- **AND** no "metrics-server not installed" errors occur