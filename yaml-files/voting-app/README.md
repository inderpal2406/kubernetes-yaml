# Voting app using kubernetes.

### Commands used to create the kubernetes objects for voting app.

kubectl get pods  # check existing pods if any.
kubectl get services  # Only default kubernetes service running.
kubectl create -f 00-voting-app-pod.yml
kubectl create -f 07-voting-app-service.yml
kubectl get pods,services
#### Check by browsing the URL of the above voting app service.
kubectl create -f 02-redis-pod.yml
kubectl create -f 05-redis-service.yml
kubectl get pods,services
kubectl create -f 03-postgres-pod.yml
kubectl create -f 06-postgres-service.yml
kubectl get pods,services
kubectl create -f 04-worker-app-pod.yml
kubectl get pods,services
kubectl create -f 01-result-app-pod.yml
kubectl create -f 08-result-app-service.yml
#### Check by browsing the URL of the result app service.
#### Above section was for deploying the microservices apps in voting app using pods.
#### Below section is for deploying the microservices apps in voting app using deployments.
#### After this we created the deployment files. Then executed below commands:
kubectl get objects  # Check if any already deployed object (pod/service/deployment)
kubectl create -f 09-voting-app-deployment.yml
kubectl create -f 07-voting-app-service.yml
kubectl get deployments
kubectl create -f 10-redis-deployment.yml
kubectl create -f 05-redis-service.yml
kubectl create -f 11-postgres-deployment.yml
kubectl create -f 06-postgres-service.yml
kubectl get deployments
kubectl get pods,services
kubectl create -f 12-worker-app-deployment.yml
kubectl get deployments
kubectl get pods,services
kubectl create -f 13-result-app-deployment.yml
kubectl create -f 08-result-app-service.yml
kubectl get deployments,pods,services
#### Get URLs for voting app service and result app service, browse them and test them.
#### Now upscale the number of replicas for the voting app, check new pods and their status.
#### Got to the browser, refresh the voting app service multiple times. Each time it is served by new container.
