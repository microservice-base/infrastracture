# infrastracture
infrastracture for microservice-base project



# DEPLOYMENT
kubectl create deployment image-basket-deployment --image=keramiozsoy/image-basket --dry-run -o yaml > deployment-basket.yaml

kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-basket.yaml

kubectl create deployment image-shop-deployment --image=keramiozsoy/image-shop --dry-run -o yaml > deployment-shop.yaml

kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-shop.yaml

kubectl create deployment image-account-deployment --image=keramiozsoy/image-account --dry-run -o yaml > deployment-account.yaml

kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/deployment-account.yaml



#SERVICE
kubectl expose deployment image-shop-deployment --type=LoadBalancer --port=8001 --dry-run -o yaml > service-shop.yaml
kubectl apply -f https://raw.githubusercontent.com/microservice-base/infrastracture/master/service-shop.yaml





