## Install PostgreSQL through Helm

```
helm install warehouse-dbms --set postgresqlUsername=testUser --set postgresqlPassword=testPassword --set postgresqlDatabase=warehouse --set initdbScripts."setup\.sh"="psql warehouse < setup\.sql" bitnami/postgresql
```
