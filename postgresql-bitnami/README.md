# PostgreSQL Bitnami Chart

## Lint of the chart
```
helm lint --set postgresqlUsername=testUser --set postgresqlPassword=testPassword --set postgresqlDatabase=warehouse --set initdbScripts."setup\.sh"="psql warehouse < /docker-entrypoint-initdb\.d/setup\.sql" . --debug
```

### Create template
```
helm template warehouse-dbms --set postgresqlUsername=testUser --set postgresqlPassword=testPassword --set postgresqlDatabase=warehouse --set initdbScripts."setup\.sh"="psql warehouse < /docker-entrypoint-initdb\.d/setup\.sql" . --debug
```

## Installation
```
# Install the chart and sets an init DB via SQL script
helm install warehouse-dbms --set postgresqlUsername=testUser --set postgresqlPassword=testPassword --set postgresqlDatabase=warehouse --set initdbScripts."setup\.sh"="psql warehouse < /docker-entrypoint-initdb\.d/setup\.sql" . --debug
```

## Edits applied compared to vanilla Bitnami Chart

### Setting proper securityContexts in values.yaml
diff -r postgresql-bitnami-vanilla/values.yaml postgresql-bitnami/values.yaml

142c142
<     runAsUser: 0
---
>     runAsUser: "auto"
156c156
<   enabled: true
---
>   enabled: false
164,165c164
<   enabled: true
<   runAsUser: 1001
---
>   enabled: false

