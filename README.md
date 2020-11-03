# Steps to Deploy Thanos using (deprecated) Rancher Monitoring

# Step 0: Create s3 bucket to store metrics

# Step 1: Deploy Prometheus

* Prometheus Extra Args: 00-prometheus-operator-values.conf
* Nodeport: 01-prometheus-nodeport-svc.yaml
<!--* Ingress: 02-prometheus-thanos-ingress.yaml-->

# Step 2: Deploy Thanos

> Banzai Catalog in this example is a Global resource.

* Banzai Catalog: 03-helm-catalog.yaml
* Object-Store Config: 04-object-store-config.yaml 
* Object-Store Secret: 05-object-store-secret.yaml
* Thanos Values: 06-thanos-operator-values.yaml

# Step 3: Run Thanos

* Thanos: 07-thanos-cr.yaml
* Object Store: 08-objectstore-cr.yaml
* Store Endpoint: 09-storeendpoint-cr.yaml

# Repeat Steps 1-3 for each cluster

# Step 4: Configuring Observer Cluster

> You can remove the sample store endpoint deployed in step 3.

* Thanos: 10-thanos-cr-observer.yaml
* Ingress: 11-thanos-sample-query-ingress.yaml
* Store Endpoint: 12-external-store-endpoint.yaml
* Deploy Grafana: (From Library Catalog)
* Add Datasource: URL from 11-thanos-sample-query-ingress.yaml
