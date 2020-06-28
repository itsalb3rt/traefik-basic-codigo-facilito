# Port detection

When you image expose more that 1 port you can set this on traefik labels

```yaml
      - "traefik.http.services.app.loadbalancer.server.port=8081"
```

If you omit this you received `Bad Gateway (502)` http response, traefik dont know what port is you can used to access to you container

Build the base image for this example

```bash
$ cd docker
$ docker build -t app:v2 .
```

## Reference

[https://docs.traefik.io/routing/providers/docker/#configuration-examples](https://docs.traefik.io/routing/providers/docker/#configuration-examples)