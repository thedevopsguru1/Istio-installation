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
