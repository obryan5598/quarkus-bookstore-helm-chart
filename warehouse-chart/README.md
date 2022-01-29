# Warehouse Helm chart

The following README shows how to install the Warehouse Chart, depending from the postgresql chart, from the current source code

## Installation

Please set accordingly the *values.yaml* file, otherwise use *--set* options

```
cd warehouse-chart
helm install warehouse-chart . --debug
```

## Test
```
helm test warehouse-chart --debug --logs
```

