# dremio-k8
Deploy dremio on k8 without helm.  Use it only if you cannot use helm for whatever the reason it is.

Steps:

1. Extract the zip to a folder
2. Run the following commands (after cd'ing to templates folder)

```kubectl create configmap dremio-config --from-file=../config/
kubectl apply -f .\dremio-master.yaml
kubectl apply -f .\dremio-executor.yaml 
kubectl apply -f .\dremio-service-client.yaml 
```
Check if the pods are running with:

`kubectl get pods`

Check the IP that you need to use to view the web ui:

`kubectl get service dremio-client`