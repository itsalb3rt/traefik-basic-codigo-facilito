# Logs

In static configuration `traefik.yml` create `log` section.

```yaml
log:
  filePath: "/traefik.log"
```

Now make a sure `traefik.log` exist.

After this, create a new volume.

```yaml
- ./traefik.log:/traefik.log
```

You can define log level with `level` instruction.

```yaml
log:
  level: DEBUG # Other leves: PANIC, FATAL, ERROR, WARN, and INFO.
```

You can change the log format.

```yaml
format: json
```

## References

[https://docs.traefik.io/observability/logs/](https://docs.traefik.io/observability/logs/)