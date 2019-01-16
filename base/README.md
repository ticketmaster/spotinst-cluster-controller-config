# Base configuration

```yaml
commonLabels:
  app: spotinst-cluster-controller
```

Add this label to every resource and use it in any `selector`.

```yaml
imageTags:
- name: spotinst/kubernetes-cluster-controller
  newTag: 1.0.28
```

Use these tags for every container image with the given names.

```yaml
namespace: kube-system
```

Install resources into this namespace.

```yaml
resources:
- certs-secret.yaml
- deployment.yaml
- rbac.yaml
```

Create the resources defined within these files.
