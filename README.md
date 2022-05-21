## nginx-proxy-ssl

nginx-proxy sets up a container running nginx and letsencrypt, generating SSL certificates.

run
```
$ docker compose up -d
$ echo "127.0.0.1     test.local whoami.local" >> /etc/hosts
$ curl g1130.synology.me
$ curl test.local:8080
$ curl -H "Host: whoami.local" whoami.local:8080
```
debug
```
docker-compose up -d && docker-compose logs letsencrypt
docker-compose logs -f letsencrypt
```
* forwarding rule router 0.0.0.0:80 -> www-host:8080
* CNAME record adrian.freisinger.com.ar ADDRESS g1130.synology.me. 