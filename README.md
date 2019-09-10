# infrastracture
infrastracture app of simple project
https://microservice-base.github.io

# CREATE NAMESPACE
```
kubectl create namespace namespace-microservice-base --dry-run -o yaml > namespace-microservice-base.yaml
kubectl create -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/namespace-microservice-base.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/namespace-microservice-base.yaml
```


# DEPLOYMENT

 ```
kubectl create deployment image-shop-deployment --image=keramiozsoy/image-shop --dry-run -o yaml > deployment-shop.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-shop.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-shop.yaml

kubectl create deployment image-basket-deployment --image=keramiozsoy/image-basket --dry-run -o yaml > deployment-basket.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-basket.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-basket.yaml

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
kubectl expose deployment image-shop-deployment --type=LoadBalancer --port=8001 --target-port=8001 --dry-run -o yaml > service-shop.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-shop.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-shop.yaml
minikube service image-shop-deployment

A = echo $(minikube ip)
B = kubectl get service -o yaml | grep nodePort

open http://A/B/shop/swagger-ui.html

OR

minikube service image-ui-deployment --url

**

kubectl expose deployment image-basket-deployment --type=LoadBalancer --port=8002 --target-port=8002 --dry-run -o yaml > service-basket.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-basket.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-basket.yaml
minikube service image-basket-deployment

A = echo $(minikube ip)
B = kubectl get service -o yaml | grep nodePort

open http://A/B/basket/

or 

minikube service image-basket-deployment --url

**

kubectl expose deployment image-account-deployment --type=LoadBalancer --port=8003 --target-port=80 --dry-run -o yaml > service-account.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-account.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-account.yaml
minikube service image-account-deployment

A = echo $(minikube ip)
B = kubectl get service -o yaml | grep nodePort

open http://A/B/account/

or

minikube service image-account-deployment --url

**

kubectl expose deployment image-payment-deployment --type=LoadBalancer --port=8004 --target-port=8004 --dry-run -o yaml > service-payment.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-payment.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-payment.yaml
minikube service image-payment-deployment

A = echo $(minikube ip)
B = kubectl get service -o yaml | grep nodePort

open http://A/B/payment/ 

or 

minikube service image-payment-deployment --url

**

kubectl expose deployment image-ui-deployment --type=LoadBalancer --port=8005 --target-port=3000 --dry-run -o yaml > service-ui.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-ui.yaml
kubectl delete -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-ui.yaml
minikube service image-ui-deployment

A = echo $(minikube ip)
B = kubectl get service -o yaml | grep nodePort

open http://A/B/ui/ (this app context will change as /ui)

or

minikube service image-ui-deployment --url

```



