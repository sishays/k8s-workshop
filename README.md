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


## Pod design
1. kubectl get pods --show-labels
2. kubectl run nginx-dev1 --image nginx --labels=env=dev 
 
   kubectl run nginx-dev2 --image nginx --labels=env=dev

   kubectl run nginx-dev3 --image nginx --labels=env=dev

   kubectl run nginx-prod1 —-image nginx --labels=env=prod

   kubectl run nginx-prod2 —-image nginx --labels=env=prod

3. kubectl get pod —-show-labels
4. kubectl get pod -l env=dev
5. kubectl get pods -l env=dev --show-labels
6. kubectl get pod -l env=prod
7. kubectl get pod -l env=prod —show-labels
8. kubectl get pod -L env
9. kubectl get pod -l 'env in (dev,prod)'
10. kubectl get pod -l 'env in (dev,prod)' --show-labels
11. kubectl label pod/nginx-dev1 env=uat --overwrite

    kubectl get pod —show-labels

12. kubectl label pod nginx-dev{1..3} env-

    kubectl label pod nginx-prod{1..2} env-
    
    kubectl get pod --show-labels
13. kubectl label pod nginx-dev{1..3} app=nginx
    
    kubectl label pod nginx-prod{1..2} app=nginx
    
    kubectl get po --show-labels
14. kubectl get nodes --show-labels
15. kubectl label node worker nodeName=nginx-node   
16. kubectl create -f pod-nginx.yaml
17. kubectl describe po nginx | grep Node-Selector
18. kubectl describe po nginx | grep Labels

## Deployment
1. webapp.yaml file
2. 
