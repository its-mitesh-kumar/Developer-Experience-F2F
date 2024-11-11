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
3. 