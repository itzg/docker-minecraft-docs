The [examples](https://github.com/itzg/docker-minecraft-bedrock-server/blob/master/examples) directory contains [an example Kubernetes manifest file](https://github.com/itzg/docker-minecraft-bedrock-server/blob/master/examples/kubernetes.yml) that declares:

- a peristent volume claim (using default storage class)
- a pod deployment that uses the declared PVC
- a service of type LoadBalancer

The pod deployment includes some examples of configuring the server properties via environment variables:

``` yaml
env:
- name: EULA
  value: "TRUE"
- name: GAMEMODE
  value: survival
- name: DIFFICULTY
  value: normal
```

The file is deploy-able as-is on most clusters, but has been confirmed on [Docker for Desktop](https://docs.docker.com/docker-for-windows/kubernetes/) and [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/docs/):

``` bash
kubectl apply -f examples/kubernetes.yml
```

You can follow the logs of the deployment using:

``` bash
kubectl logs -f deployment/bds
```
