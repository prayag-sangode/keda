
# Make sure minikube or any k8s is installed

    kubectl get all
    kubectl create ns http-scaling-test
    kubectl -n http-scaling-test apply -f httpd-deploy.yaml  
    kubectl -n http-scaling-test apply -f httpd-scaledobject.yaml 
    kubectl -n http-scaling-test get all 
    kubectl -n http-scaling-test get hpa
    kubectl -n http-scaling-test get scaledobject

# Run inside the container

    kubectl -n http-scaling-test exec -it <container-id> -- /bin/bash

# Install siege

    apt-get update && apt-get -y install stress-ng

# Generate load

    stress-ng --cpu 0 --cpu-load 60 --timeout 60s

# Check

    kubectl -n http-scaling-test get all
    kubectl -n http-scaling-test get hpa
    kubectl -n http-scaling-test get scaledobject

