Deploy the app to a Kubernetes cluster

```
git clone https://github.com/chingchiaw/prom-data-gen.git
cd prom-data-gen

kubectl create namespace prom-data-gen
kubectl -n prom-data-gen apply -f kubernetes/
```

