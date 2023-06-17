```
istioctl install --set profile=demo
```
### Check what’s installed
```
kubectl -n istio-system get deploy
```
### Display the list of available profiles
```
istioctl profile list
```
### The default Istio installation uses automatic sidecar injection. Label the namespace that will host the application with istio-injection=enabled:
```
kubectl label namespace nshere istio-injection=enabled
```
### Uninstall Istio
```
istioctl uninstall --purge
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
