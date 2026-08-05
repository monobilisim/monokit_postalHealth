# postalHealth Roadmap

Postal mail server health plugin. Feature parity with monokit1 `postalHealth/`.

## Scaffolding

- [X] Plugin skeleton from pluginTemplate (go.mod, justfile, Containerfile, test harness)
- [X] Shared example config `config/mail.yml` (postal section)
- [ ] Config struct + `mail.yml` case wired into monokit_lib
- [ ] Podman integration tests

## Features

- [ ] postal systemd service check
- [ ] Docker container checks (API connection alarm + per-container running-state alarms)
- [ ] Per health-<service> unit alarms
- [ ] MySQL connectivity from Postal config credentials (per-database alarms)
- [ ] Message queue count vs message-threshold
- [ ] Held messages per server vs held-threshold
- [ ] Redmine issue when the database is down
- [ ] Postal version reporting (monokit2: osHealth vlib `postal.go`)
