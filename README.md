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
| `image`                             | ownCloud image                            | `bitnami/owncloud:{VERSION}`                |
| `imagePullPolicy`                   | Image pull policy                         | `IfNotPresent`                              |
| `owncloudHost`                      | ownCloud host to create application URLs  | `nil`                                       |
| `owncloudLoadBalancerIP`            | `loadBalancerIP` for the owncloud Service | `nil`                                       |
| `owncloudUsername`                  | User of the application                   | `user`                                      |
| `owncloudPassword`                  | Application password                      | Randomly generated                          |
| `owncloudEmail`                     | Admin email                               | `user@example.com`                          |
| `mariadb.mariadbRootPassword`       | MariaDB admin password                    | `nil`                                       |
| `serviceType`                       | Kubernetes Service type                   | `LoadBalancer`                              |
| `persistence.enabled`               | Enable persistence using PVC              | `true`                                      |
| `persistence.apache.storageClass`   | PVC Storage Class for Apache volume       | `nil` (uses alpha storage class annotation) |
| `persistence.apache.accessMode`     | PVC Access Mode for Apache volume         | `ReadWriteOnce`                             |
| `persistence.apache.size`           | PVC Storage Request for Apache volume     | `1Gi`                                       |
| `persistence.owncloud.storageClass` | PVC Storage Class for ownCloud volume     | `nil` (uses alpha storage class annotation) |
| `persistence.owncloud.accessMode`   | PVC Access Mode for ownCloud volume       | `ReadWriteOnce`                             |
| `persistence.owncloud.size`         | PVC Storage Request for ownCloud volume   | `8Gi`                                       |
| `resources`                         | CPU/Memory resource requests/limits       | Memory: `512Mi`, CPU: `300m`                |
