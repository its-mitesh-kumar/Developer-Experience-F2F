1. Go to `ConfigMaps` edit  `app-config-rhdh`

2. 

2. Add auth block (app level)

```
auth:
      # see https://backstage.io/docs/auth/ to learn about auth providers
      environment: development
      providers:
        github:
          development:
            clientId: <clientId>
            clientSecret: <clientSecret>
            # signIn:
            #   resolvers:
            #     # typically you would pick one of these
            #     - resolver: usernameMatchingUserEntityName

```
3.  Add Catalog Snippets 

```
catalog:
  import:
    entityFilename: catalog-info.yaml
    pullRequestBranchName: backstage-integration
  rules:
    - allow: [Component, System, Group, Resource, Location, Template, API]
  locations:
    - type: url
      target: https://github.com/its-mitesh-kumar/nationalparks-py/blob/master/catalog-info.yaml
      rules:
        - allow: [User, Group]
```