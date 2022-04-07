Deploy the app to a Kubernetes cluster

```
git clone https://github.com/chingchiaw/prom-data-gen.git
cd prom-data-gen

# Connect to the cluster
gcloud edge-cloud container clusters get-credentials [cluster_name] --location [region] --project [project]

# Deploy the app
kubectl create namespace prom-data-gen
kubectl -n prom-data-gen apply -f kubernetes/

# Get the metrics endpoint response 
kubectl -n prom-data-gen port-forward service/prometheus-data-generator 9000:9000
curl localhost:9000/metrics/
```

For additional documentation about the sample app, e.g. how to change the configmap to export other metric types, please see the original README: https://github.com/chingchiaw/prom-data-gen/blob/main/old-README.md
