## (How do we persist data in k8s)
                       IF  PODS ARE EPHEMERAL

1.Deploy a pod called nginx-pod with the image nginx and 
2.inside the pod create a file text1.txt  inside one of the directories(tmp) saying 
“i love devops” and inside file text.txt echo  today's date
3. Kill this pod nginx-pod
4. Create the pod back and check if the files are still there inside that directory

## Solution
Run k get pod -A
k get ns -A

1.To create nginx-pod

k run nginx-pod --image=nginx

k exec -it nginx-pod --sh

cd tmp
ls
exit

To add the volume mount
vi volume.yaml
Put the data in the file and save
k apply -f volume.yaml

to check if the pod is running
k get pods

k exec pod-with-no-volume -it -- sh

cd var/log
ls
cat output.log

To delete pod 
k delete -f volume.yaml
k get pods *to see if the pod is still there 
Repeat the process again and check if file is still intact.




2.To create a text.txt file inside the directory (tmp) and run echo "I love devops"
vi nginx-pod.sh



To get Resource quota
kubectl create quote reqQuota --hard=cpu1,memory=IG,pod=2 --dry -run=client --variable

