# Make sure minikube or any k8s is installed
kubectl get all
kubectl create ns cpu-test
kubectl -n cpu-test apply -f httpd-deploy.yaml  
kubectl -n cpu-test apply -f httpd-scaledobject.yaml 
kubectl -n cpu-test get all 
kubectl -n cpu-test get hpa
kubectl -n cpu-test get scaledobject

# Run inside the container
kubectl -n cpu-test exec -it <container-id> -- /bin/bash

# Install siege
apt-get update && apt-get -y install stress-ng

# Generate load
stress-ng --cpu 0 --cpu-load 60 --timeout 60s

# Check
kubectl -n cpu-test get all
kubectl -n cpu-test get hpa
kubectl -n cpu-test get scaledobject

