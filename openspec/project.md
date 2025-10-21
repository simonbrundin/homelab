# Project Context

## Purpose
This project manages a personal homelab infrastructure using Kubernetes. The goal is to deploy and maintain self-hosted services like dashboards (Dashy and Homepage) in a production-like environment, providing a centralized hub for accessing various homelab applications.

## Tech Stack
- Kubernetes (container orchestration)
- Kustomize (configuration management and overlays)
- Helm (package management for Kubernetes applications)
- YAML (configuration files)
- Git (version control)

## Project Conventions

### Code Style
- Use YAML for all Kubernetes manifests
- Follow Kubernetes naming conventions (lowercase, hyphens for separators)
- Indent with 2 spaces in YAML files
- Use descriptive names for resources (e.g., service names, namespaces)
- Comment complex configurations inline

### Architecture Patterns
- Use Kustomize overlays for environment-specific configurations (base + prod overlay)
- Separate concerns with dedicated directories for each service (dashy/, homepage/)
- Leverage Helm charts for complex applications with values.yaml for customization
- Use namespaces for logical separation of services

### Testing Strategy
- Manual validation of Kubernetes manifests using `kubectl apply --dry-run`
- Test deployments in a local cluster before production
- Monitor service health through Kubernetes dashboards and logs
- No automated testing currently; rely on manual verification

### Git Workflow
- Use main branch for production-ready configurations
- Create feature branches for new service additions or changes
- Commit messages follow conventional format: "feat: add [service]", "fix: update [config]"
- Pull requests required for changes to production overlays

## Domain Context
Homelab environment focuses on self-hosting applications for personal use. Key concepts include:
- Dashy: A self-hosted dashboard for organizing links and services
- Homepage: Another dashboard application for homelab management
- Kubernetes overlays: Environment-specific customizations (prod for production deployment)

## Important Constraints
- Runs on macOS (Darwin) platform
- Limited to personal homelab scale (no high availability requirements)
- Must work with local Kubernetes cluster (e.g., minikube, k3s)
- Network constraints: Services exposed via HTTP routes

## External Dependencies
- Dashy Helm chart (external repository)
- Homepage Helm chart (external repository)
- Metrics Server Helm chart (kubernetes-sigs/metrics-server)
- Kubernetes cluster (local or cloud-based)
- Ingress controller for HTTP routing
