# Banzai Cloud Logging Operator

### Questo repository contiene i file che utilizziamo per _deployare_ la soluzione.

Installazione dell'operator

````bash
helm repo add banzaicloud-stable https://kubernetes-charts.banzaicloud.com
helm repo update
helm upgrade --install --wait --create-namespace --namespace infra logging-operator banzaicloud-stable/logging-operator
````

## Logging Resource
Il file [`LoggingResource.yaml`](`LoggingResource.yaml`) permette di definire la risorsa logging, crea i pod di fluentd e fluent-bit.

## Cluster Output
Nel file [`ClusterOutput.yaml`](ClusterOutput.yaml) sono indicate le configurazioni relative a fluentd come per esempio:

- index template
- ILM policy
- nome indice
- ...

## Cluster Flow
Nel file [`ClusterFlowOutput.yaml`](ClusterFlowOutput.yaml) sono indicate le configurazioni relative al tipo ti _parser_ utilizzato e alle _label_ per specificare i pod da cui recuperare i log.

## Secret
Nel file [`secretIndexTemplate.yaml`](secretIndexTemplate.yaml) è definita la ILM policy.

## 🔧 TODO

- [ ] ...
## License

This project is open source and available under the [GNU General Public License v3.0](LICENSE).
