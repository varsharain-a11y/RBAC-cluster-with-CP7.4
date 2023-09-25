# RBAC-cluster-with-CP7.4
CP Version used is 7.4.1
This setup uses SASL_PLAINTEXT for RBAC setup.

# LDAP setup :
This setup uses and Online LDAP test server https://www.forumsys.com/2022/05/10/online-ldap-test-server/
refer sample server.properties for ldap configuration.

# Broker/MDS Setup 
It is a 3 ZK- 3 Kafka server setup with c3 running in one of the brokers on AWS ec2 instances .
MDS cluster is running on same cluster on all 3 CP nodes . 
refer sample server.properties and control-center-production.properties for configuration.

# RoleBinding
Before starting C3 add System admin role to the c3 user , here gauss user, euler is being provided systemAdmin roles.

After brokers and MDS is up login to Confluent CLI using MDS URL:

~~~
confluent login --url http://0.0.0.0:8090
~~~


~~~
confluent iam rbac role-binding create --principal User:euler --role SystemAdmin --kafka-cluster zZAvCRqgQ1OZNumPCozEsg
~~~



