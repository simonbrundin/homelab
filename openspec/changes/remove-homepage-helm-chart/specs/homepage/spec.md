## ADDED Requirements
### Requirement: Homepage Service Deployment
The system SHALL deploy Homepage as a Kubernetes service using direct manifests, providing a dashboard for homelab applications.

#### Scenario: Service deployed successfully
- **WHEN** the Homepage manifests are applied to the cluster
- **THEN** a Homepage pod is running
- **AND** the service is accessible at the configured ingress host

#### Scenario: Kubernetes integration enabled
- **WHEN** Homepage is deployed
- **THEN** it can access Kubernetes API for cluster information
- **AND** displays cluster metrics and resources

#### Scenario: Configuration mounted
- **WHEN** Homepage starts
- **THEN** configuration files (services.yaml, widgets.yaml, etc.) are mounted from ConfigMap
- **AND** the dashboard displays configured services and widgets