# Percona Monitoring and Management

## DBaaS
https://docs.percona.com/percona-monitoring-and-management/using/dbaas.html

## PMM Client
https://www.percona.com/doc/kubernetes-operator-for-pxc/monitoring.html

1. Enable PMM Client
```
k edit perconaxtradbclusters.pxc.percona.com mysql-tpebnkcld001

  pmm:
    enabled: true
    image: percona/pmm-client:2
    resources:
      requests:
        cpu: 300m
        memory: 150M
    serverHost: 20.97.17.60
    serverUser: admin
```

2. Set admin password
```
k edit secrets dbaas-mysql-tpebnkcld001-pxc-secrets

pmmserver: YOUR_PASSWORD_BASE64
```

## Validating the Employee Data

https://dev.mysql.com/doc/employee/en/employees-validation.html

```
SET GLOBAL pxc_strict_mode=DISABLED;
```
