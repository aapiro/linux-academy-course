Learning Objectives
check_circle
Create a yaml file containing the pod spec for the nginx pod.

Create a file in /home/cloud_user/nginx.yml with this content:

apiVersion: v1
kind: Pod
metadata:
  name: nginx
  namespace: web
spec:
  containers:
  - name: nginx
    image: nginx
    command: ["nginx"]
    args: ["-g", "daemon off;", "-q"]
    ports:
    - containerPort: 80

check_circle
Create the pod.

Create the pod from the yaml file:

kubectl create -f /home/cloud_user/nginx.yml

You should see the pod listed with this command:

kubectl get pods -n web

It should have a status of Running.
