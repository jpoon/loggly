# loggly

[loggly](http://loggly.com/) is a cloud-based log managment and anlytics service.

## Introduction

This chart bootstraps a loggly deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.4+ with Beta APIs enabled
- PV provisioner support in the underlying infrastructure

## Installing the Chart

To install the chart with the release name `my-release`:

The command deploys loggly on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following tables lists the configurable parameters of the ownCloud chart and their default values.

|              Parameter              |                Description                |                   Default                   |
|-------------------------------------|-------------------------------------------|---------------------------------------------|
| `image.respository`                 | Image Location                            | `garland/kubernetes-fluentd-loggly`   |
| `image.tag`                         | Image Version                             | `1.0`   |
| `image.pullPolicy`                  | Image pull policy                         | `IfNotPresent`                              |
| `loggly.url`                        | Loggly URL                                | `nil`                                       |
| `resources`                         | CPU/Memory resource requests/limits       | Memory: `512Mi`, CPU: `300m`                |
