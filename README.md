# quarkus-bookstore-helm-chart

This README shows how to install the Warehouse Chart, depending on the postgres chart, from the current repo.


## Installation warehouse-chart
```
helm install warehouse-chart --set route.enabled=true --set route.host=warehouse-chart.your-cluster.com quarkus-bookstore-helm-repo/warehouse-chart --debug
```

## Test

To test the chart, run the command:
```
helm test warehouse-chart --debug --logs
```

It shows whether the warehouse MicroService can reach the Postgresql Database with a simple query
