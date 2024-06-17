# Make sure minikube or any k8s is installed
kubectl get all
kubectl create ns cron-test
kubectl -n cron-test apply -f httpd-deploy.yaml  
kubectl -n cron-test apply -f httpd-scaledobject.yaml 
kubectl -n cron-test get all 
kubectl -n cron-test get hpa
kubectl -n cron-test get scaledobject

# Check
kubectl -n cron-test get all
kubectl -n cron-test get hpa
kubectl -n cron-test get scaledobject

