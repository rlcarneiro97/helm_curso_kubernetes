# curso-k8s

![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)  ![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square)

A app for k8s

# Prerequisites

## Kubectl

Install ``kubectl`` command.

```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version --client
```

## Helm

Install ``helm`` command.

```bash
VERSION=v3.2.4
HELM_TAR_FILE=helm-$VERSION-linux-amd64.tar.gz

wget https://get.helm.sh/${HELM_TAR_FILE}

tar -xvzf ${HELM_TAR_FILE}

chmod +x linux-amd64/helm

sudo cp linux-amd64/helm /usr/bin/helm

rm -rf ${HELM_TAR_FILE} linux-amd64

helm version
```

# Installing the Chart

* First, access a Kubernetes cluster.

* Change the values according to the need of the environment in ``api-gateway/values.yaml`` file.

* Create namespace ``NAMESPACE`` in Kubernetes cluster.

```bash
kubectl create namespace NAMESPACE
```

* List all releases using follow command:

```bash
helm list --all --all-namespaces
```

## Parameters

The following tables lists the configurable parameters of the chart and their default values.

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"nginx:1.19.2"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| livenessProbe.failureThreshold | int | `5` |  |
| livenessProbe.initialDelaySeconds | int | `60` |  |
| livenessProbe.path | string | `"/"` |  |
| livenessProbe.periodSeconds | int | `10` |  |
| livenessProbe.successThreshold | int | `1` |  |
| livenessProbe.timeoutSeconds | int | `5` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.initialDelaySeconds | int | `45` |  |
| readinessProbe.path | string | `"/"` |  |
| readinessProbe.periodSeconds | int | `5` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `5` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"500m"` |  |
| resources.limits.memory | string | `"512Mi"` |  |
| resources.requests.cpu | string | `"100m"` |  |
| resources.requests.memory | string | `"128Mi"` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `nil` |  |
| tolerations | list | `[]` |  |

Change the values according to the need of the environment in ``values.yaml`` file.
