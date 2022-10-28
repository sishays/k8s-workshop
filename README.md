# k8s-workshop

1. kubectl run nginx-pod --image=nginx:alpine
2. kubectl run messaging --image=redis:alpine --labels=tier=msg 
3. kubectl create namespace apx-x998-ishay
4. kubectl get node -o json > /tmp/nodes-ishay.json
5. kubectl expose pod messaging --port=6379 --name=messaging-service
6. kubectl create service clusterip messaging-service --tcp=6379 --dry-run=client -o yaml > messaging-service.yaml
7. 
