# kubectl plugin for Proto

A TOML plugin for installing the Kubernetes `kubectl` CLI with [Proto](https://moonrepo.dev/proto).

## Installation

Add the plugin and a Kubernetes version to `.prototools`.

```toml
kubectl = "1.37.2"

[plugins.tools]
kubectl = "https://github.com/BarretoTech/proto-kubectl-plugin/releases/download/v0.1.0/plugin.toml"
```

Run `proto install kubectl`, then `kubectl version --client`.

## Supported platforms

The manifest supports Linux, macOS, and Windows x64 and arm64 binaries. Proto currently distributes its Windows CLI for x64. The plugin downloads official binaries from `dl.k8s.io` and verifies each download against its published SHA-256 checksum. CI runs fresh installations on Linux x64 and arm64, macOS x64 and arm64, and Windows x64 with Proto 0.63.2.

## Development

Point a `.prototools` plugin locator at `file://./plugin.toml` and run `proto install kubectl`, `proto bin kubectl`, and `kubectl version --client`. Each CI smoke test uses a fresh Proto home and tests the pinned Kubernetes version and the latest stable release.

Releases contain `plugin.toml` and `plugin.toml.sha256`. The TOML includes community catalog metadata so it can also be contributed to `moonrepo/community-plugins`.

## License

MIT. Kubernetes and kubectl are maintained by the Kubernetes project.
