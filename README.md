# Real-World DevOps Problems & Solutions

**Problem**  
HPA was not scaling even with high CPU load  
**Solution**  
Metrics Server was missing. Installed it and verified it was collecting metrics with `kubectl top pod`.

**Problem**  
Custom metrics not available for autoscaling  
**Solution**  
Used Prometheus Adapter to expose `anomaly_count` metric to Kubernetes API.

**Problem**  
GitHub webhook didn’t trigger Jenkins pipeline  
**Solution**  
Jenkins was on localhost. Used `ngrok` to expose it and registered the public webhook URL.

**Problem**  
`docker push` to Harbor fails — TLS error  
**Solution**  
Used self-signed cert without SAN. Regenerated proper SAN-enabled cert and trusted it inside Docker.

**Problem**  
Kibana shows empty dashboards  
**Solution**  
Index pattern was not created. Manually defined the index and time field.


**Problem**  
CloudTrail logs not appearing in OpenSearch  
**Solution**  
S3 bucket policy blocked access. Updated IAM role to allow `s3:GetObject`.


**Problem**  
Harbor TLS cert rejected by Kubernetes  
**Solution**  
Docker didn’t trust the cert. Manually copied it inside Minikube and local Docker.

**Problem** 
Curl to public IP fails, but works with Minikube IP.
**Solution**  
kubectl port-forward --address 0.0.0.0 service/sample-app-service 8080:80

**Problem** 
Service not routing to all pod versions
**Solution**  
Used kubectl patch to remove version: v1 from the Service selector so that both v1 and v3 pods can receive traffic (app: sample-app matches both).

**Problem** 
Patch Command Didn't Apply Correctly (No Change)
**Solution** 
JSON patch format worked.


