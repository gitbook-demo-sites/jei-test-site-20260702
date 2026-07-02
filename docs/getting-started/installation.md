# Installation

Orbitly is a web app — no installation required. But the CLI and desktop app make daily workflows faster.

## CLI

### macOS / Linux

```bash
curl -fsSL https://get.orbitly.example.com | sh
```

Or with Homebrew:

```bash
brew install orbitly/tap/orbitly
```

### Windows

```powershell
winget install Orbitly.CLI
```

### Verify

```bash
orbitly --version
# orbitly 3.2.1
```

## Authenticate the CLI

```bash
orbitly login
```

This opens a browser window for OAuth. To use an API token instead (CI environments):

```bash
export ORBITLY_TOKEN=orb_live_xxxxxxxxxxxx
orbitly whoami
```

## Desktop app

Download from `orbitly.example.com/download`. Available for macOS (Apple Silicon and Intel), Windows 10+, and Linux (AppImage and .deb).

## System requirements

| Platform | Minimum |
| -------- | ------- |
| Browser | Chrome 100+, Firefox 100+, Safari 16+ |
| macOS | 12 Monterey |
| Windows | Windows 10 21H2 |
| CLI | Any 64-bit OS |
