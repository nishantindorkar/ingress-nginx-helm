# ingress-nginx-helm

eksctl create cluster -f new-cluster.yaml

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm install sample-ingress ingress-nginx/ingress-nginx -f values.yaml

kubectl apply -f 011/sample-app.yaml

dig +short www.devopsbyexample.io  #verify DNS


# development 
kubectl get deployments -n sample
kubectl delete deployment sample-hello -n sample

# clean up
helm repo remove ingress-nginx
eksctl delete cluster -f new-cluster.yaml
