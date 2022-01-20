== System requirements

- Docker
- mkcert

== Clear data

Swipe data from docker/mongo/data & docker/mysql/data for a clean install

== Launch

Go to docker-compose up -d
- Visit localhost:8080
- Visit dev.test

== Dry run

```
$ sudo nano /etc/hosts
# when the system is booting.  Do not change this entry.
##
127.0.0.1       localhost
127.0.0.1       dev.test
$ cd certs
$ mkcert -install
$ mkcert -cert-file dev.test.crt -key-file dev.test.key dev.test localhost 127.0.0.1 ::1
```