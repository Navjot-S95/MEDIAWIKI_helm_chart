# MEDIAWIKI_helm_chart
# MediaWiki

MediaWiki is the free and open source wiki software that powers Wikipedia. Used by thousands of organizations, it is extremely powerful, scalable software and a feature-rich wiki implementation.

[Overview of MediaWiki](http://www.mediawiki.org/wiki/MediaWiki)


## Introduction

This chart bootstraps a [MediaWiki](https://hub.docker.com/r/bitnami/mediawiki/) deployment on a [Kubernetes](https://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

It also packages the [mariadb](https://hub.docker.com/r/bitnami/mariadb/) deployment on k8s as dependency chart.


## Prerequisites

- Kubernetes 1.19+
- Helm 3.2.0+
- PV provisioner support in the underlying infrastructure
- ReadWriteMany volumes for deployment scaling

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install mywiki ediawiki
```

The command deploys MediaWiki on the Kubernetes cluster in the default configuration.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete mywiki
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters

### Mediawiki parameters

| Name                 | Description                                                                                                                                        | Value                 |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- |                                                                                 
| `image.repository`   | MediaWiki image repository                                                                                                                         | `bitnami/mediawiki`   |
| `image.tag`          | MediaWiki image tag (immutable tags are recommended)                                                                                               | `1.38.2-debian-11-r2` |
| `image.pullPolicy`   | Image pull policy                                                                                                                                  | `IfNotPresent`        |
| `persistence.size`   | PVC size for mediawiki                                                                                                                             | `1Gi`                 |
| `updateStrategy.type`| StrategyType can be set to RollingUpdate or OnDelete                                                                                               | `RollingUpdate`       |
