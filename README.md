# k8s-workshop

1. kubectl run nginx-pod --image=nginx:alpine
2. kubectl run messaging --image=redis:alpine --labels=tier=msg 
3. kubectl create namespace apx-x998-ishay
4. kubectl get node -o json > /tmp/nodes-ishay.json
5. kubectl expose pod messaging --port=6379 --name=messaging-service
6. kubectl create service clusterip messaging-service --tcp=6379 --dry-run=client -o yaml > messaging-service.yaml
7. kubectl create deployment hr-web-app --image odekloud/webapp-color --replicas 2
8. kubectl run static-busybox --image=busybox  -o yaml --command -- sleep 1000 --dry-run=client > /etc/kubernetes/manifests/static-busybox.yaml
9. kubectl create ns finance-ishay
   
   kubectl -n finance-ishay run temp-bus --image redis:alpine
10.  Stored as pv-analytics.yaml
11. Stored as redis-storage-ishay.yaml
12. ??
13.  Using nginx-deploy.yaml

kubectl create -f nginx-deploy.yaml --record 

kubectl set image deploy nginx-deploy nginx=nginx:1.17 --record 

kubectl rollout history deploy nginx-deploy

<img width="611" alt="image" src="https://user-images.githubusercontent.com/89786937/198843559-a18e9d0e-264b-4039-bf56-a5be31e938a6.png">
15. 
