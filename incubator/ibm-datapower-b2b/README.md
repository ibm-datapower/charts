# IBM Datapower B2B Gateway 

![IDG Logo](https://avatars1.githubusercontent.com/u/8836442?v=4&s=200)

[IBM® DataPower Gateway](http://www-03.ibm.com/software/products/en/datapower-gateway) is a purpose-built security and integration gateway that addresses the business needs for mobile, API, web, SOA, B2B, and cloud workloads. It is designed to provide a consistent configuration-based approach to security, governance, integration and routing.


## Introduction

This chart deploys the IBM DataPower B2B Gateway using a StatefulSet and claimTemplates to get per replica volume claims to support the b2b persistance requirement.

 ## Installing the Chart
 To install the chart with the release name `my-release` and default pattern (See .Values.patternName below):
 ```bash
$ helm install --name my-release -f <mycrypto.yaml> stable/ibm-datapower-dev
```

> **Tip**: List all releases using `helm list`
## Verifying the Chart
See NOTES.txt associated with this chart for verification instructions

 ## Uninstalling the Chart
To uninstall/delete the `my-release` deployment:

```bash
$ helm delete my-release
```

## Configuration
The helm chart has the following Values that can be overriden using the install `--set` parameter or by providing your own values file. For example:

`helm install --set image.repository=<myimage> stable/datapower`

| Value                              | Description                                   | Default             |
|------------------------------------|-----------------------------------------------|---------------------|
| `replicaCount`                     | The replicaCount for the deployment           | 2                   |
| `image.repository`                 | The image to use for this deployment          | ibmcom/datapower    |
| `image.tag`                        | The image tag to use for this deployment      | latest              |
| `image.pullPolicy`                 | Determines when the image should be pulled    | IfNotPresent        |
| `service.name`                     | Name to add to service                        | datapower           |
| `env.acceptLicense`                | License Acceptance                            | true                |
| `resources.limits.cpu`             | Container CPU limit                           | 8                   |
| `resources.limits.memory`          | Container memory limit                        | 64Gi                |
| `resources.requests.cpu`           | Container CPU requested                       | 4                   |
| `resources.requests.memory`        | Container Memory requested                    | 8Gi                 |


Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example,

```bash
$ helm install --name my-release -f values.yaml stable/datapower
```

> **Tip**: You can use the default [values.yaml](values.yaml)

[View the official IBM DataPower Gateway for Developers Docker Image in Docker Hub](https://hub.docker.com/r/ibmcom/datapower/)

[View the IBM DataPower Gateway Product Page](http://www-03.ibm.com/software/products/en/datapower-gateway)

[View the IBM DataPower Gateway Documentation](https://www.ibm.com/support/knowledgecenter/SS9H2Y)
