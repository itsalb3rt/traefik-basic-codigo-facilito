# Reverse Proxy by Path

If you want access to you container by path name whiout set this path inside your contianer, required use the `StripPrefix` Middleware.

For exmaple if you use a simple container of `ngnix` and set a simple rule using `path` you can see log message like this.

```text
[error] 21#21: *1 open() "/usr/share/nginx/html/traefik" failed (2: No such file or directory),
```

for solved this you can added the `StripPrefix` middleware

```yaml
- "traefik.http.middlewares.test-stripprefix.stripprefix.prefixes=/traefik" # Path to remove
- "traefik.http.routers.nginx.middlewares=test-stripprefix" # Used declared middleware
```

What this does is remove the prefix before calling the container and so not pass the prefix as a path


## References

[https://docs.traefik.io/middlewares/stripprefix/](https://docs.traefik.io/middlewares/stripprefix/)