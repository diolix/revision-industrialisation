// docker pull wordpress

1) minikube delete
2) minikube start --driver=docker
3) kubectl apply -f test.yaml
4) kubectl get pods
5) minikube service wordpress-service --url

0) kubectl delete pods --all -n default 