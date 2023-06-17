# Istio-installation

```
helm repo add istio https://istio-release.storage.googleapis.com/charts
```
```
helm repo update
```
#### Create the namespace, istio-system, for the Istio components:
```
kubectl create namespace istio-system
```
## Install the Istio base chart which contains cluster-wide Custom Resource Definitions (CRDs) which must be installed prior to the deployment of the Istio control plane
```
helm install istio-base istio/base -n istio-system 
```
#### Validate the CRD installation with the helm ls command
```
helm ls -n istio-system
```
## Install the Istio discovery chart which deploys the istiod service
```
helm install istiod istio/istiod -n istio-system --wait
```
#### Verify the Istio discovery chart installation
```
helm ls -n istio-system
```
#### Get the status of the installed helm chart to ensure it is deployed
```
helm status istiod -n istio-system
```
#### Check istiod service is successfully installed and its pods are running
```
kubectl get deployments -n istio-system --output wide
```

## Install an ingress gateway:
```
kubectl create namespace istio-ingress
```
```
helm install istio-ingress istio/gateway -n istio-ingress --wait
```
## Label the namespace of you application
```
kubectl label namespace yournamespacehere istio-injection=enabled
```
### 
https://artifacthub.io/packages/helm/istio-official/istiod
###
https://artifacthub.io/packages/helm/istio-official/gateway
###
https://artifacthub.io/packages/helm/istio-official/base
# Install Kiali
```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.17/samples/addons/kiali.yaml
```
# Do the same thing for the rest of adds-on
https://istio.io/latest/docs/ops/integrations/
```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.17/samples/addons/grafana.yaml
```
```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.17/samples/addons/jaeger.yaml
```
```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.17/samples/addons/prometheus.yaml
```
```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.17/samples/addons/extras/zipkin.yaml
```
