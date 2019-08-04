# infrastracture
infrastracture app of simple project

# NAMESPACE
```
kubectl create namespace namespace-microservice-base --dry-run -o yaml > namespace-microservice-base.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/namespace-microservice-base.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/namespace-microservice-base.yaml




```




# DEPLOYMENT

 ```
kubectl create deployment image-basket-deployment --image=keramiozsoy/image-basket --dry-run -o yaml > deployment-basket.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-basket.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-basket.yaml


kubectl create deployment image-shop-deployment --image=keramiozsoy/image-shop --dry-run -o yaml > deployment-shop.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-shop.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-shop.yaml

kubectl create deployment image-account-deployment --image=keramiozsoy/image-account --dry-run -o yaml > deployment-account.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-account.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-account.yaml

kubectl create deployment image-ui-deployment --image=keramiozsoy/image-ui --dry-run -o yaml > deployment-ui.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-ui.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-ui.yaml

kubectl create deployment image-payment-deployment --image=keramiozsoy/image-payment --dry-run -o yaml > deployment-payment.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-payment.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-payment.yaml



```

# SERVICE
```
kubectl expose deployment image-shop-deployment --type=LoadBalancer --port=8001 --dry-run -o yaml > service-shop.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-shop.yaml

```



