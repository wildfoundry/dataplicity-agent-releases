# Dataplicity agent releases

Public install packages for the Dataplicity Prelude agent. This repository
holds **release artefacts only** (wheelhouses and `.deb` packages). Agent
development stays private.

## Install

Copy the command from the Dataplicity dashboard and run it on the Linux device:

```sh
curl -fsSL https://install.dataplicity.com/install/<key>.sh | sudo bash
```

That script downloads the matching wheelhouse from this repo. Do not install
from PyPI.

## Packages

Releases attach:

| Asset | Use |
| --- | --- |
| `dataplicity-agent_<version>_<arch>-wheelhouse.tar.gz` | Default installer payload (`amd64`, `arm64`, `armhf`) |
| `dataplicity-agent_<version>_<arch>.deb` | Optional Debian package with a vendored venv |

See [Releases](https://github.com/wildfoundry/dataplicity-agent-releases/releases)
for downloadable files.

## More information

https://www.dataplicity.com/
