# custom-template

Basically the same as the nginx-ingress chart, but using a custom template to include some other content

<image src="./charts/README.md">

## Additional Information

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm repo add foo-bar http://charts.foo-bar.com
$ helm install my-release foo-bar/custom-template
```

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| @stable | nginx-ingress | 0.22.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| controller.extraVolumes[0].configMap.name | string | `"nginx-ingress-config"` | Uses the name of the configmap created by this chart |
| controller.extraVolumes[0].name | string | `"config-volume"` |  |
| controller.image.repository | string | `"nginx-ingress-controller"` |  |
| controller.image.tag | string | `"18.0831"` |  |
| controller.ingressClass | string | `"nginx"` | Name of the ingress class to route through this controller |
| controller.name | string | `"controller"` |  |
| controller.persistentVolumeClaims | list | the chart will construct this list internally unless specified | List of persistent volume claims to create. For very long comments, break them into multiple lines. |
| controller.podLabels | object | `{}` | The labels to be applied to instances of the controller pod |
| controller.publishService.enabled | bool | `false` | Whether to expose the ingress controller to the public world |
| controller.replicas | int | `nil` | Number of nginx-ingress pods to load balance between |
| controller.service.annotations."external-dns.alpha.kubernetes.io/hostname" | string | `"stupidchess.jmn23.com"` | Hostname to be assigned to the ELB for the service |
| controller.service.type | string | `"LoadBalancer"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
