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