## ADDED Requirements

### Requirement: Stalwart Mail Server Deployment

The system SHALL provide a Stalwart Mail Server instance running as a HelmRelease in Kubernetes.

#### Scenario: Stalwart deploys via FluxCD
- **GIVEN** FluxCD is configured in the cluster
- **WHEN** the stalwart HelmRelease is applied
- **THEN** a Stalwart pod SHALL start in the `stalwart` namespace
- **AND** the PostgreSQL database SHALL be configured and available

#### Scenario: Stalwart uses PostgreSQL backend
- **GIVEN** Stalwart HelmRelease is deployed
- **WHEN** the service is configured
- **THEN** it SHALL use external PostgreSQL instead of local SQLite
- **AND** local persistence SHALL be disabled

### Requirement: SMTP Service

The system SHALL provide SMTP service for email.

#### Scenario: SMTP ports are exposed
- **WHEN** Stalwart is deployed
- **THEN** port 25 (SMTP), 465 (SMTPS), and 587 (Submission) SHALL be configured

### Requirement: IMAP/JMAP Service

The system SHALL provide IMAP and JMAP access for mail clients.

#### Scenario: IMAP and JMAP ports are exposed
- **WHEN** Stalwart is deployed
- **THEN** port 143 (IMAP), 993 (IMAPS), and 8080 (JMAP HTTP) SHALL be configured

### Requirement: Web Interface

The system SHALL provide a web interface for mail administration.

#### Scenario: Web interface is accessible
- **WHEN** Stalwart is deployed
- **THEN** the web interface SHALL be accessible via `https://mail.simonbrundin.com`

### Requirement: Persistent Storage

The system SHALL use Longhorn for persistent storage of mail data.

#### Scenario: Mail data is persisted
- **WHEN** Stalwart is deployed
- **THEN** mail data and index SHALL be saved on a Longhorn PVC
- **AND** data SHALL survive pod restarts

### Requirement: Secret Management

Database passwords SHALL be managed as Kubernetes Secrets, not in plain manifests.

#### Scenario: Database password is protected
- **WHEN** database configuration is created
- **THEN** the password SHALL be stored in a Kubernetes Secret
- **AND** referenced via secretKeyRef in HelmRelease
