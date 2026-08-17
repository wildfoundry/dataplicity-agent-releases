# Dataplicity Agent

A resilient agent runtime for secure device updates. This repository publishes
**install packages only** (wheelhouses and `.deb` files). Development stays in
a private repository.

## About

When you install the Dataplicity Agent on a Linux device, it establishes and
maintains a secure connection to Dataplicity so you can reach the device
without opening inbound ports.

This package ships both generations of the runtime side by side:

- **Dataplicity Agent (rescue plane)** — remote shell, wormhole, and porthole.
  This path must stay bulletproof and low-dependency.
- **Prelude Supervisor** — container, firmware, and device-class reconcile
  (the update manager).

Both daemons share a single device identity under `/var/lib/dataplicity/`.

## How it works

The agent opportunistically maintains an encrypted connection to the Dataplicity
IoT Router. Remote shell, Wormhole, and related traffic are routed over that
session, so NAT, firewalls, and dynamic IPs are not blockers.

For more information, see https://docs.dataplicity.com and
https://www.dataplicity.com/.

## Install

Copy the command from the Dataplicity dashboard and run it on the Linux device:

```sh
curl -fsSL https://install.dataplicity.com/install/<key>.sh | sudo bash
```

That script downloads the matching wheelhouse from this repo. Do not install
from PyPI.

## Packages

See [Releases](https://github.com/wildfoundry/dataplicity-agent-releases/releases)
for downloadable files.

| Asset | Use |
| --- | --- |
| `dataplicity-agent_<version>_<arch>-wheelhouse.tar.gz` | Default installer payload (`amd64`, `arm64`, `armhf`) |
| `dataplicity-agent_<version>_<arch>.deb` | Optional Debian package with a vendored venv |

Latest: [v0.1.47](https://github.com/wildfoundry/dataplicity-agent-releases/releases/tag/v0.1.47) (amd64).

## License

Dataplicity agent is licensed under a modified-BSD license. See
[LICENSE.txt](LICENSE.txt).
