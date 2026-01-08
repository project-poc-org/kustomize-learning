# Kustomize Learning Repository

Comprehensive Kustomize examples with overlays and components.

## Usage

```bash
# Dev
kustomize build overlays/dev | kubectl apply -f -

# Staging
kustomize build overlays/staging | kubectl apply -f -

# Production  
kustomize build overlays/prod | kubectl apply -f -
```

See documentation for complete examples.
