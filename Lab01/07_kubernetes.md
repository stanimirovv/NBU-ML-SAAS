The prerequisite is to have microk8s installed and running.

First install the necessery plugins
```
microk8s enable dns
microk8s enable host-access
```

Generate the helm chart

```
microk8s.helm create mlnbu-example
```

Validate that the generation works:
```
microk8s.helm install mlnbu-example mlnbu-example/
microk8s.helm delete mlnbu-example
```

microk8s.kubectl get pods


In the values file set the port correctly
and adjust the image

Then, move the docker image to the microk8 registry

docker save nbu2023:latest | microk8s ctr images import -


Debugging:
```
microk8s.kubectl logs
microk8s.kubectl describe pod 
```

Now that you know the issue - fix it and redeploy.