# Patch Operator

Kubernetes patch operator, fork from [redhat-cop/patch-operator](https://github.com/redhat-cop/patch-operator).

## Install

### cert-manager

```shell
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.9.1/cert-manager.yaml
```

### patch-operator

```shell
make deploy IMG=registry.cn-hangzhou.aliyuncs.com/hb-chen/patch-operator:latest@sha256:3ff7d9b62b6f8a9a9ef12ce49ebbb2050236bd71d214f7efc8d33ae6eb9d44c0
```

### samples

```shell
# apply inject webhook
kubectl apply -n patch-system -f config/samples/01_webhook_inject.yaml

kubectl apply -n patch-system -k config/samples
```

```shell
source-object-name-0=patch-controller-manager
source-object-name-1=patch-system
source-object-name-2=patch-controller-manager
```

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

```shell
make docker-build docker-push IMG=registry.cn-hangzhou.aliyuncs.com/hb-chen/patch-operator:latest

make deploy IMG=registry.cn-hangzhou.aliyuncs.com/hb-chen/patch-operator:latest
```
