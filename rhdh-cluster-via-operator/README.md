# Deploying an instance of Backstage using a Helm Chart on OpenShift

### Prerequisites

- OpenShift cluster

### Janus Backstage Helm Chart

1.  Login into OpenShift cluster web-console

2.  Create a namespace `backstage-workshop`

3.  Install `Red Hat Developer Hub Operator` operator

4.  Select `Current namespace only ` and click on  `Create Backstage` and then  `Create` . 

5. Select the `Topology` view, and click the Open URL icon on the Developer Hub pod to identify your Developer Hub external URL: <RHDH_URL>

6. Go to `Create ConfigMap` , select yaml 
```
kind: ConfigMap
apiVersion: v1
metadata:
  name: app-config-rhdh
  namespace: mitesh
data:
  app-config-rhdh.yaml: |
    app:
      title: Red Hat Developer Hub
      baseUrl: <RHDH_URL>
    backend:
      # Used for enabling authentication, secret is shared by all backend plugins
      # See https://backstage.io/docs/auth/service-to-service-auth for
      # information on the format
      auth:
        dangerouslyDisableDefaultAuthPolicy: true
        keys:
          - secret: 'gh'

```

7. Click the overflow menu for the Red Hat Developer Hub instance that you want to use and select `Edit Backstage` to load the YAML view of the Red Hat Developer Hub instance.Add 
```
mountPath: /opt/app-root/src
      configMaps:
        - name: app-config-rhdh
```
