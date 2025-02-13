![logo](https://raw.githubusercontent.com/dexidp/website/9ac240c84d3e34766814cd9ece76710cf075ba23/static/favicons/favicon.png){ align="right", width="100" }
# Dex

## Installation
This service template is typically pre-installed in k0rdent. If not
install it:
~~~bash
helm install dex oci://ghcr.io/k0rdent/catalog/charts/dex-service-template -n kcm-system
~~~

Check the template is available:
~~~bash
kubectl get servicetemplates -A
# NAMESPACE    NAME             VALID
# kcm-system   dex-0-19-1       true
~~~

## Usage
Use the template in k0rdent manifests `ClusterDeployment` or `MultiClusterService`:
~~~yaml
apiVersion: k0rdent.mirantis.com/v1alpha1
kind: ClusterDeployment
# kind: MultiClusterService
...
  serviceSpec:
    services:
      - template: dex-0-19-1
        name: dex
        namespace: dex
~~~

## References
- [Official docs](https://dexidp.io/docs/)
