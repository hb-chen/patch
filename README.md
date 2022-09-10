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

## Run It On the Cluster
```shell
make docker-build docker-push IMG=registry.cn-hangzhou.aliyuncs.com/hb-chen/patch-operator:latest
```

```shell
make deploy IMG=registry.cn-hangzhou.aliyuncs.com/hb-chen/patch-operator:latest
```

## cert-manager

```shell
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.9.1/cert-manager.yaml
```