# Spider-Rainbows Platform Configuration

GitOps repository for spider-rainbows Kubernetes manifests managed by ArgoCD.

## Structure

```
/
├── argocd/                          # ArgoCD self-management (future)
├── spider-rainbows/                 # Spider-rainbows application manifests
│   ├── deployment.yaml              # Deployment with 2 replicas
│   ├── service.yaml                 # ClusterIP service
│   └── ingress.yaml                 # Ingress for nip.io access
└── README.md
```

## Application Access

- **App URL**: http://spider-rainbows.127.0.0.1.nip.io
- **Health Check**: http://spider-rainbows.127.0.0.1.nip.io/health

## ArgoCD Management

This repository is watched by ArgoCD running in the `spider-rainbows-gitops` Kind cluster.

Changes to manifests in this repo are automatically synced to the cluster (auto-sync enabled).

## Image Updates

The CI/CD pipeline in the spider-rainbows application repository updates the image tag in `deployment.yaml` when new versions are built.

Current image: `wiggitywhitney/spider-rainbows:1.0.0`
