## Task1
I. Create a single pod of image httpd:alpine3.20 in namespace application (check if namespace exist or not)

Pls the pod should be name web1 and the container should be name web-container


Ii. Write  a shell script to output the status of the pod

## Solution
1.Use interactive command()
To creat pod with a yaml file
 k run web1 --namespace=application --image=httpd:alpine3.20 --dry-run=client -o yaml > pod.yaml

 2.Run vi pod.yaml
 press i the edit the container name to web-container
 press esc and then save by typing :wq! Then save

 3.To create your pod is a running start
 k apply -f pod.yaml

To tell if application in terms of yaml
 kubectl -n application get pod web1  -o yaml

To give the output in terms of Json
kubectl -n application get pod web1  -o json

kubectl -n application get pod web1  -o jsonpath={.status}

To get status of your pod

To write shell
vi web1-status.sh
Do bash scripting of the following command
kubectl -n application get pod web1  -o jsonpath={.status.phase}
input the command inside the script ensure you start command with #!/bin/bash,copy the command inside the script press escape and type :wq! and enter.
type chmod 777 web1-status.sh (enter)
type ./web1-status.sh
# cat web1-status.sh
status must be running
k exec -it web1 -n application --sh 
ls into file and cd into temps or logs
echo "i love devops cloud computing">output.txt
cat output.txt
exit
