## Overview

This repository contains the infrastructure definitions for our Kubernetes management and workload clusters. We use CAPI with the OpenStack provider (CAPO) to declaratively manage cluster lifecycle across production and non-production environments.

## Structure

- `clusters/` - Environment-specific cluster configurations
  - `management/` - Management cluster Flux configuration
  - `nonprod/` - Non-production environment
  - `prod/` - Production environment
- `infrastructure/` - Platform components
  - `bootstrap/` - CAPI operator and base providers
  - `openstack/` - OpenStack provider and credentials
- `workload-clusters/` - Workload cluster definitions
  - `nonprod/` - Non-production workload clusters
  - `prod/` - Production workload clusters

## Prerequisites

- Management cluster with Flux installed
- OpenStack credentials configured
- kubectl and clusterctl CLI tools

## Deployment

The management cluster automatically reconciles changes via Flux. To add a new workload cluster:

1. Create cluster manifests in `workload-clusters/{env}/`
2. Add kustomization reference in `clusters/{env}/kustomization.yaml`
3. Commit and push - Flux handles the rest

## Notes

All clusters use Calico CNI and are configured with appropriate ClusterResourceSets for bootstrapping. OpenStack credentials are managed as sealed secrets per environment.
