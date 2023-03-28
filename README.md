[![Build Status](https://github.com/eaxdev/MySQL-NDB-example-with-ClusterJ/workflows/build/badge.svg)](https://github.com/eaxdev/MySQL-NDB-example-with-ClusterJ/actions)
[![codecov](https://codecov.io/gh/eaxdev/MySQL-NDB-example-with-ClusterJ/branch/master/graph/badge.svg)](https://codecov.io/gh/eaxdev/MySQL-NDB-example-with-ClusterJ)

# MySQL-NDB-example-with-ClusterJ
This is example for using `MySQL NDB Cluster` (via `ClusterJ` library).
 
Using:
* `SpringBoot`
* `ClusterJ`
* `TestContainers`
* `JUnit5`

Preparation for launch: 

* Install `docker`

* Download `NDB ClusterJ (Java Connector for NDB)` library and install 
it via package manager: https://dev.mysql.com/downloads/cluster/

* Download `ndbclient_7.6.9`

* add clusterj dependency via `Maven` to local repo: 
```bash
mvn install:install-file -DgroupId=com.mysql.ndb -DartifactId=clusterj -Dversion=7.6.9 -Dpackaging=jar -Dfile=clusterj-7.6.9.jar -DgeneratePom=true
```

* Run tests via `Maven`:

```bash
mvn -DargLine="-Djava.library.path=/usr/lib/x86_64-linux-gnu/" clean test
```

when `/usr/lib/x86_64-linux-gnu/` path to `ndbclient_7.6.9.so`

For example, see `.github/workflows/maven-ci-build.yml` for more details.
#### https://dev.mysql.com/doc/ndbapi/en/mccj.html
#### ---------------------------------------------
#### https://hevodata.com/learn/spring-boot-mysql/
#### https://learn.microsoft.com/es-es/azure/mysql/flexible-server/tutorial-deploy-springboot-on-aks-vnet
#### https://techcommunity.microsoft.com/t5/azure-database-for-mysql-blog/azure-open-source-day-announcing-new-integrations-with-azure/ba-p/3760771
#### https://medium.com/@bostone/how-to-run-mysql-cluster-backed-secure-spring-boot-app-on-aws-eks-74570a18a801
#### https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html
#### https://dev.mysql.com/doc/ndb-operator/en/tasks-access-within-k8s.html
#### https://stackoverflow.com/questions/54778350/run-mysql-cluster-backed-https-enabled-spring-boot-app-on-aws-eks
#### https://devpress.csdn.net/k8s/62fd822f7e6682346619266a.html
