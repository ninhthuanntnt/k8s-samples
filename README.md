# k8s-samples

## Start the Minikube
Start the minikube
```shell
minikube start
```

## Namespace
Check existing namespaces
```shell
kubectl get namespaces
```

Apply a namespace with file `namespace.yml`
```shell
kubectl apply -f <namespace-yml-file>
```

Delete a namespace with file `namespace.yml`
```shell
kubectl delete -f <namespace-yml-file>
```

Then apply the namespace again with to prepare for next steps

## Deployment
Check existing deployments
```shell
kubectl get deployments -n <namespace>
```

Apply a deployment with file `deployment.yml`
```shell
kubectl apply -f <deployment-yml-file>
```

Check existing pods
```shell
kubectl get pods -n <namespace>
```

Delete a pod and see the self-healing works
```shell
kubectl delete pod <pod-name> -n <namespace>
```

Describe a pod to view the pod details
```shell
kubectl describe pod <pod-name> -n <namespace>
```

## Use busybox to test the deployment
After applying the busybox deployment, check the pods
```shell
kubectl exec -it <busybox-pod-name> -n <namespace> -- /bin/sh
```

Check the ip address of the deployment pod in another terminal
```shell
kubectl get pods -n <namespace> -o wide
```

Back to the busybox pod terminal, ping the deployment pod ip address
```shell
wget -qO - <pod-ip-address>:<pod-expose-port>
```

Command to view the logs of pod
```shell
kubectl logs <pod-name> -n <namespace>
```

