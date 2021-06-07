# kubernetes

## Get logs for init container failures by describing the pods

```sh
kubectl describe po pod_name -n namespace
```

## Get live logs of a pod (i.e container)

```sh
kubectl logs --follow pod_name -c container_name -n namespace 
```
