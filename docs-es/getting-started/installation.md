---
description: "Instala el CLI y la aplicación de escritorio de Orbitly, luego conéctalos a tu espacio de trabajo."
icon: download
---

# Instalación

Orbitly se ejecuta en el navegador, por lo que la mayoría de los equipos pueden comenzar sin instalar nada. Instala el CLI cuando quieras flujos de trabajo locales más rápidos, operaciones automatizadas o automatización CI/CD.

{% hint style="info" %}
Usa la aplicación web para planificación y colaboración. Usa el CLI para acciones repetibles como crear misiones desde scripts, exportar telemetría o verificar la preparación de lanzamientos en CI.
{% endhint %}

## Elige tu configuración

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
      <td><strong>Aplicación web</strong></td>
      <td>Ideal para planificación, revisiones, paneles y configuración del espacio de trabajo.</td>
      <td><a href="quickstart.md">inicio rápido</a></td>
    </tr>
    <tr>
      <td><i class="fa-terminal"></i></td>
      <td><strong>CLI</strong></td>
      <td>Ideal para desarrolladores, automatización, exportaciones y flujos de trabajo con scripts.</td>
      <td><a href="#install-the-cli">instalar cli</a></td>
    </tr>
    <tr>
      <td><i class="fa-desktop"></i></td>
      <td><strong>Aplicación de escritorio</strong></td>
      <td>Ideal para triaje enfocado, notificaciones y captura rápida.</td>
      <td><a href="#desktop-app">aplicación de escritorio</a></td>
    </tr>
  </tbody>
</table>

## Instalar el CLI

{% tabs %}
{% tab title="macOS / Linux" %}
```bash
curl -fsSL https://get.orbitly.example.com | sh
```

O instala con Homebrew:

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

## Verificar la instalación

{% stepper %}
{% step %}
## Verifica la versión

```bash
orbitly --version
# orbitly 3.2.1
```
{% endstep %}

{% step %}
## Inicia sesión

```bash
orbitly login
```

Esto abre una ventana del navegador y completa OAuth para tu cuenta de usuario.
{% endstep %}

{% step %}
## Confirma tu espacio de trabajo

```bash
orbitly whoami
orbitly workspace list
```

Si perteneces a múltiples espacios de trabajo, configura uno por defecto en [Configuración](configuration.md).
{% endstep %}
{% endstepper %}

## Aplicación de escritorio

Descarga la aplicación de escritorio desde `orbitly.example.com/download`. Está disponible para macOS, Windows y Linux.

La aplicación de escritorio es útil cuando quieres:

* Notificaciones nativas para menciones, solicitudes de revisión y misiones bloqueadas
* Captura rápida desde la barra de menú o bandeja del sistema
* Una bandeja de entrada compacta de misiones para triaje diario

## Requisitos del sistema

| Plataforma | Mínimo |
| --------- | ------- |
| Navegador | Chrome 100+, Firefox 100+, Safari 16+ |
| macOS | 12 Monterey |
| Windows | Windows 10 21H2 |
| Linux | Distribución compatible con AppImage o soporte para paquetes Debian |
| CLI | Cualquier SO de 64 bits |

{% hint style="warning" %}
No uses un token API personal en máquinas compartidas o registros de CI. Crea un token de cuenta de servicio para automatización y rótalo cuando cambie la membresía del equipo.
{% endhint %}
