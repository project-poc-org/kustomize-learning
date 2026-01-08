# Kustomize Learning Repository

Master Kustomize with comprehensive examples.

## Kustomize Features Covered

### 1. Base + Overlays Pattern
- **base/**: Common resources shared across all environments
- **overlays/**: Environment-specific customizations

### 2. Patches
- **Strategic Merge Patch**: Merge new fields into existing resources
- **JSON Patch (RFC 6902)**: Precise field modifications

### 3. Generators
- **ConfigMapGenerator**: Generate ConfigMaps with hash suffixes
- **SecretGenerator**: Generate Secrets with hash suffixes

### 4. Transformers
- **namePrefix/Suffix**: Add prefixes/suffixes to resource names
- **commonLabels**: Add labels to all resources
- **commonAnnotations**: Add annotations to all resources
- **images**: Change image names/tags
- **replicas**: Override replica counts

### 5. Components
- Reusable configuration snippets
- Can be included in multiple overlays

## Structure
```
base/              # Shared base resources
overlays/
  dev/             # Development overrides
  staging/         # Staging overrides
  prod/            # Production overrides
components/
  monitoring/      # Prometheus ServiceMonitor
  redis/           # Redis deployment
```

## Usage
```bash
# View generated manifests
kustomize build overlays/dev
kustomize build overlays/prod

# Apply to cluster
kubectl apply -k overlays/dev
kubectl apply -k overlays/prod

# Diff before applying
kubectl diff -k overlays/prod
```

## Learning Path
1. Study **base/** - understand core resources
2. Compare **overlays/dev vs prod** - see differences
3. Analyze **patches** - strategic merge vs JSON
4. Explore **generators** - ConfigMap/Secret with hashes
5. Test: `kustomize build overlays/dev > output.yaml`
