# Cnvrg Workers Kubernetes Chart

Use this repo to configure your cluster for cnvrg jobs 

**Usage**

    run ./install-crds.sh to install custom resource definitions
    helm template --namespace cnvrg --name cnvrg . -f values.yaml >> all.yaml
    kubectl apply -f all.yaml



## Chart options
| **key**              | **default value** | **description**
| ----------| :------|:--- |
| global.namespace|cnvrg| Namespace to install components
| global.domain|-| Domain for cluster services, for example: clippers.apps.cnvrg.io
| global.domain_access_key|-| Access key to route53, for writing domain
| global.domain_secret_key|-| Secret key to route53, for writing domain
| global.domain_hosted_zone_id|-| Route53 Hosted zone id
| global.app_domain|-| Domain for cluster services, for example: clippers.apps.cnvrg.io
| global.node_selectors | true | Should use node selectors for each component (db, app)
| global.gke| false | Whether its running on GKE - Google Kubernetes Engine 
| istio.enabled | true | Install istio for inbound traffic
| istio.serviceType | LoadBalancer | Whether istio will use NodePort or Load Balancer for exposing its services
| cert-manager.enabled | true | Use cert manager to sign this domain (using route53)
| prometheus.enabled | true | Install prometheus for cluster monitoring
| grafana.enabled | false | Install grafana for monitoring visualization
| fluentd.enabled | true | Run fluentd for cnvrg logs collection
| nvidia-device-plugin.enabled | false | Install nvidia device plugin for installing and mounting gpu devices 
