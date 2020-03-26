## A simple hello world war application
Use standard javax api and it contains a simple servlet, package as war application.

## How to Build
./mvnw clean package

Deploy the target/helloworld-1.0.0.war to any application server(tomcat, wildfly, EAP or websphere etc)

## Deploy Example (Assuming in linux terminal)

1. Download wildfly
```shell
wget https://download.jboss.org/wildfly/19.0.0.Final/wildfly-19.0.0.Final.zip
cd /tmp
unzip wildfly-19.0.0.Final.zip

```

2. Deploy to wildfly
```shell
cp /.../simple-war/target/helloworld-1.0.0.war /tmp/wildfly-servlet-19.0.0.Final/standalone/deployments/helloworld.war
```

3. Start wildfly (Step 2 can be sorted after wildfly started)
```shell
cd /tmp/wildfly-servlet-19.0.0.Final/bin
./standalone.sh
```
A deployment succesful message should be shown in the console
```
14:41:53,401 INFO  [org.wildfly.extension.undertow] (ServerService Thread Pool -- 79) WFLYUT0021: Registered web context: '/helloworld' for server 'default-server'
14:41:53,495 INFO  [org.jboss.as.server] (ServerService Thread Pool -- 45) WFLYSRV0010: Deployed "helloworld.war" (runtime-name : "helloworld.war")
14:41:53,576 INFO  [org.jboss.as.server] (Controller Boot Thread) WFLYSRV0212: Resuming server
14:41:53,579 INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0060: Http management interface listening on http://127.0.0.1:9990/management
14:41:53,579 INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0051: Admin console listening on http://127.0.0.1:9990
14:41:53,579 INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0025: WildFly Full 19.0.0.Final (WildFly Core 11.0.0.Final) started in 6796ms - Started 446 of 673 services (379 services are lazy, passive or on-demand)
```
4. Access by browser
http://localhost:8080/helloworld
