# example overlay

```yaml
bases:
# - github.com/ticketmaster/spotinst-cluster-controller-config//base
- ../../base
```

Use the manifests in the `/base` directory of this repository as the base for this overlay.

```yaml
commonLabels:
  app: spotinst-cluster-controller
  inventoryCode: spotinst-cluster-controller
  productCode: prd354
```

Add/substitute these labels on every resource created by the base & overlay and use them in any `selector`.

```yaml
namespace: prd354
```

Install resources into this namespace.

```yaml
patches:
- deployment.yaml
```

Apply these patches to the resources they describe.

```yaml
secretGenerator:
- name: spotinst-cluster-controller
  commands:
    ACCOUNT: "printf act-1234ab56"
    CLUSTER_IDENTIFIER: "printf my_cluster"
    TOKEN: "printf 2x2783548814xeax98d7a41771268a99f6758abxdec04b6b7f20d3995eb9205b"
  type: Opaque
```

Generate a secret with these keys and values set to the output of the provided shell commands.
