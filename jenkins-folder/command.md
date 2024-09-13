## Deployment of jenkins application on Kubernetes
kubectl get node

alias k=kubectl

k get nodes

k create namespace jenkins

k get ns

k delete namespace dev

k get pods -n jenkins

k apply -f deployment.yaml -n jenkins

k describe pod <pod name> -n <namespace>

k apply -f service.yaml -n <namespace>

minikube service <servicename> -n <namespace>

k delete -f service.yaml -n <namespace>
k delete -f deployment.yaml -n <namespace>

#Before you apply you must first delete
# This command we use to get into our pod and save file
 k exec -it nginx-deployment-77d8468669-5ztwl -- sh
k exec -it jenkins-f56c6888f-b489w -n <podname> -- sh
#ls
#cd tmp
#echo "I love Devops".output.txt
#cat output.txt
Exit