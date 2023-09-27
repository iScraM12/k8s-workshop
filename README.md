# k8s-worksho pcheat sheet
## Namespace wechseln
kubectl config set-context --current --namespace=kube-public

## Mit Pod interagieren
```
kubectl apply -f 010_create_pod.yml
kubectl get all
kubectl get pod
kubectl get pod rover-service -o wide
kubectl get pod rover-service -o json
kubectl get pod rover-service -o jsonpath="PodIP {.status.podIP}"
kubectl describe pod/rover-service
kubectl logs rover-service
kubectl exec rover-service -- ls -la
kubectl delete -f 010_create_pod.yml
```

## Pods/Deployments erkunden
```
kubectl apply -f 020_create_deployment.yml
kubectl get pods -l app=rover-service
kubectl get deployment rover-service -o wide
```

## Applikation bereitstellen

### tl;dr

```
kubectl apply -f 022_create_deployment.yml
```
deployment.apps/rover created
```
kubectl apply -f 031_create_service.yml
```
service/rover-service created
```
kubectl apply -f 040_create_ingress.yml
```
ingress.networking.k8s.io/rover-ingress created

### Im Browser 
### URL: http://rover-service.internal/rover-service/api/properties/hostname

```
kubectl apply -f 051_create_ui-deployment.yml
```
deployment.apps/rover-ui created

```
kubectl apply -f 060_create_ui-service.yml
```
service/rover-ui-service created

```
kubectl apply -f 070_create_ui-ingress.yml
```
ingress.networking.k8s.io/rover-ui-ingress created

### Im Browser 
### URL: http://rover-service.internal/assets/json/config.json

```
kubectl apply -f 080_create_ui-configMap.yml
```
configmap/rover-ui-config created

### Im Browser 
### URL: http://rover-service.internal

```
rffffffffffffflflflflflfffffrrffffflflflflflfffffffffffff
```
