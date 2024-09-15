## Task 4
I. Create a Resource Quota called “reqQuota '' with hard limits of 1 CPU,!G memory and  pods without creating it.
Ii. Get pods on all namespaces

## Solution
To create resource quota we can check for the command using

k create resourcequota --help

we use the command 
kubectl create quota reqQuota --hard=cpu=1,memory=1G,pods=2 --dry-run=client --validate -o yaml > 5.yaml

To get all pods on Namespaces we use

k get ns -A
 k get pods -A