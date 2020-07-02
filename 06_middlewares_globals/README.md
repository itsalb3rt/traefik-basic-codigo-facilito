# Globals Middlewares

If you want use a global middleware only define this in the main `traefik` service.

**Global basic auth**

```yaml
    labels: 
      - "traefik.http.routers.redirs.rule=HostRegexp(`{host:.+}`)" # Apply to all host
      - "traefik.http.middlewares.test-auth.basicauth.users=admin:$$apr1$$ZAhx0FA1$$G8.pUHAJA2ImgGRejJS2d/" # Define user and password
      - "traefik.http.routers.redirs.middlewares=test-auth" # Set auth middleware
```

## Image

```bash
$ cd docker
$ docker build -t app:v2 .
```

## Reference

[https://docs.traefik.io/routing/routers/](https://docs.traefik.io/routing/routers/)