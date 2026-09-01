# postalHealth Roadmap

Postal mail server health plugin. Feature parity with monokit1 `postalHealth/`.

## Scaffolding

- [X] Plugin skeleton from pluginTemplate (go.mod, justfile, Containerfile, test harness)
- [X] Shared example config `config/mail.yml` (postal section)
- [ ] Config struct + `mail.yml` case wired into monokit_lib
- [ ] Podman integration tests

## Features

- [ ] Postal installation auto-detection, so deleting the config disables the plugin
- [ ] postal systemd service check
- [ ] Docker container checks (API connection alarm + per-container running-state alarms)
- [ ] Per health-<service> unit alarms
- [ ] MySQL connectivity from Postal config credentials (per-database alarms)
  - [ ] Separate alarm when the Postal config file itself cannot be read
- [ ] Message queue count vs message-threshold
  - [ ] Distinct alarm for "cannot query message_db" vs "queue over the limit"
- [ ] Held messages per server vs held-threshold
- [ ] SSL certificate check on the SMTP port (monokit1 `postalHealth/ssl.go`)
  - [ ] Port 25 STARTTLS handshake, leaf certificate read
  - [ ] Connection-failure alarm (`postal_sslcert_conn`)
  - [ ] No-certificate-presented alarm (`postal_sslcert_nocert`)
  - [ ] Expiring-soon alarm vs the configured threshold in days, recovery clears it
- [ ] Redmine issue when the database is down
- [ ] Postal version reporting (monokit2: osHealth vlib `postal.go`)
- [ ] Health summary box output (depends on the lib renderer)
- [ ] Health data POST to the server API (depends on base client/server API)
