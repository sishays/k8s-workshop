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
1. kubectl create -f webapp.yaml
2. kubectl rollout status deployment webapp
3. kubectl get rs -l app=webapp
4. kubectl get rs -l app=webapp -o yaml > webapp-rs.yaml

   kubectl get pods -l app=webapp -o yaml > webapp-pods.yaml
   
5. kubectl delete deployment webapp
6. kubectl create -f webapp2.yaml
7. kubectl set image deployment webapp nginx=nginx:1.17.4

   kubectl describe deployment webapp | grep -i image
8. kubectl rollout history deployment webapp
9. kubectl rollout undo deployment webapp

   kubectl describe deployment webapp | grep -i image
  
10. kubectl set image deployment webapp nginx=nginx:1.100

    kubectl rollout status deployment webapp 
    
    kubectl rollout undo deployment webapp

    kubectl rollout status deployment webapp
    
11. kubectl autoscale deployment webapp --min=10 --max=20 --cpu-percent=85

    kubectl get hpa
    
    kubectl get pod -l app=webapp
    
12. kubectl delete deployment webapp

    kubectl delete hpa webapp
    
## configMap
1. Created config.txt
2. kubectl create cm keyvalcfgmap --from-file=config.txt

   kubectl get cm keyvalcfgmap -o yaml > keyvalcfgmap.yaml
