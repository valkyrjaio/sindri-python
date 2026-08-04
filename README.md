<p align="center"><a href="https://valkyrja.io" target="_blank">
    <img src="https://raw.githubusercontent.com/valkyrjaio/art/refs/heads/master/long-banner/orange/python.png" width="100%">
</a></p>

# Sindri

[Sindri][github sindri] is the build tool and application creator for the
[Valkyrja][Valkyrja url] Python framework.

Sindri scaffolds new Valkyrja applications, generates cache files for faster
runtime performance, and handles build-time concerns across the Valkyrja
ecosystem. Named after the dwarven smith in Norse mythology who forged Mjölnir
and other divine artifacts, Sindri does for your Valkyrja app what his namesake
did for the gods: crafts the tools and artifacts that make it all work faster
and better.

<p>
    <a href="https://pypi.org/project/valkyrja-sindri/"><img src="https://img.shields.io/pypi/v/valkyrja-sindri.svg" alt="Latest Version on PyPI"></a>
    <a href="https://pypi.org/project/valkyrja-sindri/"><img src="https://img.shields.io/pypi/pyversions/valkyrja-sindri.svg" alt="Supported Python Version"></a>
    <a href="https://github.com/valkyrjaio/sindri-python/blob/26.x/LICENSE.md"><img src="https://img.shields.io/github/license/valkyrjaio/sindri-python.svg" alt="License"></a>
    <a href="https://github.com/valkyrjaio/sindri-python/actions/workflows/ci.yml?query=branch%3A26.x"><img src="https://github.com/valkyrjaio/sindri-python/actions/workflows/ci.yml/badge.svg?branch=26.x" alt="CI Status"></a>
</p>

Status
------

Warning: the Python port is in progress. This repository holds the package, the
CI pipeline, and the release process. It does not hold the build tool yet.
Install the package to reserve the dependency, and do not build on it yet.

PHP is the reference implementation, and every other port mirrors its structure,
its naming, and its tests. Read [`PORTS.md`][ports url] for the state of each
language.

What Sindri Does
----------------

The list below is what the port delivers. Each item exists in the PHP reference
implementation today.

- **Scaffolds new Valkyrja applications** — bootstraps a fresh project with the
  correct structure, entry points, and configuration
- **Generates cache files** — produces the compiled container, event, and
  routing data that lets an application skip discovery work at runtime
- **Builds artifacts** — prepares deployable output for a production runtime
- **Handles upgrades** — assists with a migration between major Valkyrja
  versions

Sindri reads the provider tree with the standard library `ast` and `inspect`
modules. The framework itself carries no build dependency and no AST
dependency.

Installation
------------

Sindri is a development dependency. It never ships to production.

```bash
uv add --dev valkyrja-sindri
```

```bash
pip install valkyrja-sindri
```

**Python 3.14 or later is required.**

Getting Started
---------------

### Scaffolding a New Application

```bash
sindri new your-app-name
```

This creates a project directory with pre-wired HTTP and CLI entry points,
example controllers and commands, and a complete configuration scaffold. It is
equivalent to the [`valkyrja-starter-app-python`][starter url] template, driven
from the command line.

### Building Cache Files

```bash
sindri cache
```

The cache removes discovery and configuration work from startup. The framework
runs without it, so the cache is an optimization rather than a requirement.

### Listing Available Commands

```bash
sindri list
```

Documentation
-------------

For framework-level questions about Valkyrja itself, see the
[Valkyrja framework repository][framework url].

Versioning and Release Process
------------------------------

Sindri follows [semantic versioning][semantic versioning url] with a major
release every year, and support for each major version for 2 years from the
date of release.

For more information see the
[Versioning and Release Process documentation][versioning url].

Contributing
------------

Sindri is an open-source, community-driven project. Thank you for your interest
in helping develop, maintain, and release it.

See [`CONTRIBUTING.md`][contributing url] for the submission process and
[`VOCABULARY.md`][vocabulary url] for the terminology that Valkyrja uses.

Security Issues
---------------

If you discover a security vulnerability within Sindri, please follow the
[disclosure procedure][security vulnerabilities url].

License
-------

Sindri is open-source software licensed under the
[MIT license][MIT license url]. See [`LICENSE.md`](./LICENSE.md).

[Valkyrja url]: https://valkyrja.io
[framework url]: https://github.com/valkyrjaio/valkyrja-python
[github sindri]: https://github.com/valkyrjaio/sindri-python
[starter url]: https://github.com/valkyrjaio/valkyrja-starter-app-python
[ports url]: https://github.com/valkyrjaio/architecture/blob/26.x/PORTS.md
[versioning url]: https://github.com/valkyrjaio/architecture/blob/26.x/VERSIONING.md
[contributing url]: https://github.com/valkyrjaio/.github/blob/26.x/CONTRIBUTING.md
[vocabulary url]: https://github.com/valkyrjaio/.github/blob/26.x/VOCABULARY.md
[security vulnerabilities url]: https://github.com/valkyrjaio/.github/blob/26.x/SECURITY.md
[semantic versioning url]: https://semver.org/
[MIT license url]: https://opensource.org/licenses/MIT
