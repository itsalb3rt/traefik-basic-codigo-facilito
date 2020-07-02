# Basic Middlewares

The `Middlewares` required 2 step, define the middleware and use the middleware in you service.

## Example basic auth

Protect route by basic http auth.

First install `apache2-utils` for generated user and hash password

```bash
$ sudo apt-get install apache2-utils
```

After install `apache2-utils` generate the user and hash password.

```bash
$ echo $(htpasswd -nb user password) | sed -e s/\\$/\\$\\$/g
```

> Replace user and password with whatever you want

Your received out similar to `admin:$$apr1$$ZAhx0FA1$$G8.pUHAJA2ImgGRejJS2d/`

Now you can set the `labels` in you `docker-compose.yml` like.

```yaml
- "traefik.http.middlewares.test-auth.basicauth.users=admin:$$apr1$$ZAhx0FA1$$G8.pUHAJA2ImgGRejJS2d/"
- "traefik.http.routers.app.middlewares=test-auth"
```

## Image

```bash
$ cd docker
$ docker build -t app:v2 .
```

## Reference

[https://docs.traefik.io/middlewares/basicauth/](https://docs.traefik.io/middlewares/basicauth/)