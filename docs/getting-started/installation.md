---
description: "Install the Orbitly CLI and desktop app, then connect them to your workspace."
icon: download
---

# Installation

Orbitly runs in the browser, so most teams can start without installing anything. Install the CLI when you want faster local workflows, scripted operations, or CI/CD automation.

{% hint style="info" %}
Use the web app for planning and collaboration. Use the CLI for repeatable actions like creating missions from scripts, exporting telemetry, or checking release readiness in CI.
{% endhint %}

## Choose your setup

<table data-view="cards">
  <thead>
    <tr>
      <th width="48"></th>
      <th></th>
      <th></th>
      <th data-hidden data-card-target data-type="content-ref"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><i class="fa-browser"></i></td>
      <td><strong>Web app</strong></td>
      <td>Best for planning, reviews, dashboards, and workspace settings.</td>
      <td><a href="quickstart.md">quickstart</a></td>
    </tr>
    <tr>
      <td><i class="fa-terminal"></i></td>
      <td><strong>CLI</strong></td>
      <td>Best for developers, automation, exports, and scripted workflows.</td>
      <td><a href="#install-the-cli">install cli</a></td>
    </tr>
    <tr>
      <td><i class="fa-desktop"></i></td>
      <td><strong>Desktop app</strong></td>
      <td>Best for focused triage, notifications, and quick capture.</td>
      <td><a href="#desktop-app">desktop app</a></td>
    </tr>
  </tbody>
</table>

## Install the CLI

{% tabs %}
{% tab title="macOS / Linux" %}
```bash
curl -fsSL https://get.orbitly.example.com | sh
```

Or install with Homebrew:

```bash
brew install orbitly/tap/orbitly
```
{% endtab %}

{% tab title="Windows" %}
```powershell
winget install Orbitly.CLI
```
{% endtab %}

{% tab title="CI" %}
```bash
curl -fsSL https://get.orbitly.example.com | sh
export ORBITLY_TOKEN="$ORBITLY_TOKEN"
orbitly whoami --json
```
{% endtab %}
{% endtabs %}

## Verify the install

{% stepper %}
{% step %}
## Check the version

```bash
orbitly --version
# orbitly 3.2.1
```
{% endstep %}

{% step %}
## Sign in

```bash
orbitly login
```

This opens a browser window and completes OAuth for your user account.
{% endstep %}

{% step %}
## Confirm your workspace

```bash
orbitly whoami
orbitly workspace list
```

If you belong to multiple workspaces, set a default in [Configuration](configuration.md).
{% endstep %}
{% endstepper %}

## Desktop app

Download the desktop app from `orbitly.example.com/download`. It is available for macOS, Windows, and Linux.

The desktop app is useful when you want:

* Native notifications for mentions, review requests, and blocked missions
* Quick capture from the menu bar or system tray
* A compact mission inbox for daily triage

## System requirements

| Platform | Minimum |
| -------- | ------- |
| Browser | Chrome 100+, Firefox 100+, Safari 16+ |
| macOS | 12 Monterey |
| Windows | Windows 10 21H2 |
| Linux | AppImage-compatible distribution or Debian package support |
| CLI | Any 64-bit OS |

{% hint style="warning" %}
Do not use a personal API token in shared machines or CI logs. Create a service account token for automation and rotate it when team membership changes.
{% endhint %}
