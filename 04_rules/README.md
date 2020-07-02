# Rules

The rules permit set a custom subdomain and path for containers

for example:

```yaml
    labels: 
      - "traefik.http.routers.nginx.rule=Host(`nginx.app.test`) || Host(`whoami.app.test`)"
```
For access to service required go to follow route: http://nginx.app.test/traefik

You can combine multiple matchers using the AND (`&&`) and OR (`||`) operators. You can also use parenthesis.

**Simple path**

For access to container with a simple path you can use a simple funcion name `Path` and pass path name.

```yaml
- "traefik.http.routers.app.rule=Path(`/app`)"
```
## References

[https://docs.traefik.io/routing/routers/#rule](https://docs.traefik.io/routing/routers/#rule)