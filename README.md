# ingress-nginx-helm

eksctl create cluster -f new-cluster.yaml

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm install sample-ingress ingress-nginx/ingress-nginx -f values.yaml

kubectl apply -f sample-app.yaml

kubectl apply -f sample-hello-v2.yaml

dig +short nishantssl.tk  #verify DNS


# development 

kubectl get deployments -n sample

kubectl delete deployment sample-hello -n sample

# clean up
helm repo remove ingress-nginx

eksctl delete cluster -f new-cluster.yaml
