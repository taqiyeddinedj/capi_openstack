leet-infra/
├── clusters/
│   ├── management/
│   │   ├── flux-system/              
│   │   ├── infrastructure.yaml     
│   │   └── workload-clusters.yaml   
│   ├── hors-prod/
│   │   └── kustomization.yaml
│   └── prod/
│       └── kustomization.yaml
├── infrastructure/
│   ├── base/
│   │   ├── capi-operator.yaml
│   │   ├── capi-providers.yaml
│   │   └── kustomization.yaml
│   └── openstack/
│       ├── provider/
│       │   ├── capo-provider.yaml
│       │   └── kustomization.yaml
│       └── credentials/
│           ├── clouds-secret.yaml
│           └── kustomization.yaml
└── workload-clusters/
    ├── hors-prod/
    │   └── cluster-01/
    │       ├── cluster.yaml
    │       ├── openstackcluster.yaml
    │       ├── kubeadmcontrolplane.yaml
    │       ├── kubeadmconfigtemplate.yaml
    │       ├── openstackmachinetemplate-controlplane.yaml
    │       ├── openstackmachinetemplate-worker.yaml
    │       ├── machinedeployment.yaml
    │       ├── clusterresourceset.yaml
    │       ├── flux-install-configmap.yaml
    │       ├── flux-sync-configmap.yaml
    │       └── kustomization.yaml
    └── prod/
        └── cluster-01/
            └── (similar structure)