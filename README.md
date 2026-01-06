# SPIRE macOS Binaries

Pre-built macOS binaries for [SPIRE](https://github.com/spiffe/spire) (SPIFFE Runtime Environment).

## Why This Exists

SPIRE doesn't publish official macOS binaries. This repository provides pre-built binaries for macOS (both Intel and Apple Silicon) to make it easier to use SPIRE on macOS without requiring users to build from source.

## Automated Builds

Binaries are built automatically using GitHub Actions from the official SPIRE source code.

## Usage with Eigenoid

The [Eigenoid SDK](https://github.com/andylow92/SPIRE-A2A-Protocol) automatically downloads and uses these binaries when running on macOS.

```bash
eigenoid start
```

## Manual Installation

Download the appropriate binary for your architecture:

```bash
# For Intel Macs (amd64)
wget https://github.com/andylow92/spire-binaries/releases/download/v1.9.6/spire-1.9.6-macos-amd64.tar.gz
tar -xzf spire-1.9.6-macos-amd64.tar.gz

# For Apple Silicon Macs (arm64)
wget https://github.com/andylow92/spire-binaries/releases/download/v1.9.6/spire-1.9.6-macos-arm64.tar.gz
tar -xzf spire-1.9.6-macos-arm64.tar.gz
```

## Security Note

These binaries are **not code-signed**. On first run, you may need to allow them in:
- System Settings > Privacy & Security > Security

Or use:
```bash
xattr -d com.apple.quarantine spire-server
xattr -d com.apple.quarantine spire-agent
```

## Building New Versions

Trigger the workflow manually via GitHub Actions with the desired SPIRE version.

## License

SPIRE is licensed under the Apache License 2.0. See the [official SPIRE repository](https://github.com/spiffe/spire) for details.
