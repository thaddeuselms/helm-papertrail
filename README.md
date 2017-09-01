# Generic Helm Chart

This is a helm templated deployment for papertrail.

## Chart details

This chart will do the following:

* The chart will deploy the log router [logspout](https://github.com/gliderlabs/logspout) as a deamonset to the current kubernetes cluster and forward logs from the docker deamon to the specificed [papertrail](https://papertrailapp.com/) log destination.


Installing the chart.
```bash
helm upgrade --install <deployment name> . -f values.yaml --namespace <namespace>
```

List the deployed charts
```bash
helm list
```
Deleting a deployed chart
```bash
helm delete <name>
```

| Parameter                        | Description                                        | Default                       |
| -------------------------------- | -------------------------------------------------- | ----------------------------- |
| ` deployment name`               | Name of deployment                                 | ``                            |
| `image.repository`               | Image file location                                | `gliderlabs/logspout`         |
| `image.tag`                      | Image tag                                          | `v2`                          |
| `image.pullPolicy`               | Image pull policy                                  | `IfNotPresent`                |
| `log.level`                      | Specify wether logs will be sent securely.         | `syslog`                      |
| `log.destination`                | Papertrail log destination.                        | ``                            |
| `log.port`                       | Papertrail log destination port                    | ``                            |
| `resources`                      | Provides resource limits                           | `{}`                          |




