# Deploying an instance of Backstage using a Helm Chart on OpenShift

### Prerequisites

- OpenShift cluster

### Janus Backstage Helm Chart

1.  Login into OpenShift cluster web-console

2.  Create a namespace `backstage-workshop`

3.  In developer perspective select `Helm Chart` 

4.  Add cluster route

5.  Create `Create ConfigMap`
```
kind: ConfigMap
apiVersion: v1
metadata:
  name: app-config-rhdh
data:
  app-config-rhdh.yaml: |
    app:
      title: Red Hat Developer Hub
```

6. Expand Root Schema -> Backstage chart schema -> Backstage parameters -> Extra app configuration files to inline into command arguments.
    Click the Add Extra app configuration files to inline into command arguments link.
    Enter the value in the following fields:

    configMapRef: app-config-rhdh
    filename: app-config-rhdh.yaml

