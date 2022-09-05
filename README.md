# patch
Kubernetes patch operator

## Kubebuilder

```shell
kubebuilder init --domain hbchen.com --repo github.com/hb-chen/patch --plugins=go/v4-alpha
```

```shell
kubebuilder create api --group patch --version v1alpha1 --kind Patch
```

```shell
kubebuilder create webhook --group patch --version v1alpha1 --kind Patch  --conversion --defaulting --programmatic-validation
```

```shell
make manifests

make install 

make run
```