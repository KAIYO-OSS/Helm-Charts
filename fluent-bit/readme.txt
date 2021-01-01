 https://medium.com/kubernetes-tutorials/exporting-kubernetes-logs-to-elasticsearch-using-fluent-bit-758e8de606af
 
This will require only 1 instance of fluent bit at cluster level
kubectl create -f serviceaccount.yml
kubectl create -f clusterrole.yml 
kubectl create -f clusterrolebinding.yml

edit elk host and port
kubectl create -f fluentbit-deploy.yml
kubectl get pods -n=fluentbit-test   
kubectl logs fluent-bit-4drgs --namespace=fluentbit-test

then just add log.info and log.err in our internal services
this will come in kibana thorugh elastic search 
the below one is our logginalert vm in azure where elk and kibana is installed
http://13.72.79.181/app/discover