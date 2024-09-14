## Task 2
i.Create a namespace called myspace and a pod with image ngnix and nginx on that namespace
ii.Create a pod that was just described using yaml
iii.Create a busybox pod that runs the command ”ls”, check the output.

## solution
To delete pod nginx mistakenly created in myspace
k delete pod nginx -n myspace
i.To create myspace and a pod (nginx) with image ngnix in that space all at once we run.This command creates a dry run of pod nginx-pod.yaml
k run nginx --namespace=myspace --image=ngnix --dry-run=client -o yaml > nginx-pod.yaml
ii.
iii.To creat a busybox pod that runs the command "ls"  we use
 k run busybox --image=busybox --command --restart=Never -it -- ls
 To checks output at the same time we use,
 k run busybox --image=busybox --restart=Never -it -- bin/bash –command echo “i  love Devops” –dry-run=client -o yaml > echo1.yaml