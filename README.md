## nginx-proxy

nginx-proxy sets up a container running nginx and docker-gen. docker-gen generates reverse proxy configs for nginx and reloads nginx when containers are started and stopped.

```
$ docker compose up -d
$ echo "127.0.0.1     test.local whoami.local" >> /etc/hosts
$ curl g1130.synology.me
$ curl test.local:8080
$ curl -H "Host: whoami.local" whoami.local:8080
```
* forwarding rule router 0.0.0.0:80 -> www-host:8080
* CNAME record adrian.freisinger.com.ar ADDRESS g1130.synology.me. 