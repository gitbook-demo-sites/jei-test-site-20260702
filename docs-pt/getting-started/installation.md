---
description: "Instale o Orbitly CLI e o aplicativo desktop, depois conecte-os ao seu workspace."
icon: download
---

# Instalação

Orbitly roda no navegador, então a maioria das equipes pode começar sem instalar nada. Instale o CLI quando quiser fluxos de trabalho locais mais rápidos, operações scriptadas ou automação CI/CD.

{% hint style="info" %}
Use o aplicativo web para planejamento e colaboração. Use o CLI para ações repetíveis como criar missões a partir de scripts, exportar telemetria ou verificar a prontidão de lançamentos no CI.
{% endhint %}

## Escolha sua configuração

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
      <td><strong>Aplicativo web</strong></td>
      <td>Melhor para planejamento, revisões, dashboards e configurações do workspace.</td>
      <td><a href="quickstart.md">quickstart</a></td>
    </tr>
    <tr>
      <td><i class="fa-terminal"></i></td>
      <td><strong>CLI</strong></td>
      <td>Melhor para desenvolvedores, automação, exportações e fluxos de trabalho scriptados.</td>
      <td><a href="#install-the-cli">install cli</a></td>
    </tr>
    <tr>
      <td><i class="fa-desktop"></i></td>
      <td><strong>Aplicativo desktop</strong></td>
      <td>Melhor para triagem focada, notificações e captura rápida.</td>
      <td><a href="#desktop-app">desktop app</a></td>
    </tr>
  </tbody>
</table>

## Instale o CLI

{% tabs %}
{% tab title="macOS / Linux" %}
```bash
curl -fsSL https://get.orbitly.example.com | sh
```

Ou instale com Homebrew:

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

## Verifique a instalação

{% stepper %}
{% step %}
## Verifique a versão

```bash
orbitly --version
# orbitly 3.2.1
```
{% endstep %}

{% step %}
## Faça login

```bash
orbitly login
```

Isso abre uma janela do navegador e completa o OAuth para sua conta de usuário.
{% endstep %}

{% step %}
## Confirme seu workspace

```bash
orbitly whoami
orbitly workspace list
```

Se você pertence a múltiplos workspaces, defina um padrão em [Configuração](configuration.md).
{% endstep %}
{% endstepper %}

## Aplicativo desktop

Baixe o aplicativo desktop em `orbitly.example.com/download`. Está disponível para macOS, Windows e Linux.

O aplicativo desktop é útil quando você quer:

* Notificações nativas para menções, solicitações de revisão e missões bloqueadas
* Captura rápida a partir da barra de menu ou bandeja do sistema
* Uma caixa de entrada compacta de missões para triagem diária

## Requisitos do sistema

| Plataforma | Mínimo |
| --------- | ------- |
| Navegador | Chrome 100+, Firefox 100+, Safari 16+ |
| macOS | 12 Monterey |
| Windows | Windows 10 21H2 |
| Linux | Distribuição compatível com AppImage ou suporte a pacote Debian |
| CLI | Qualquer SO 64-bit |

{% hint style="warning" %}
Não use um token de API pessoal em máquinas compartilhadas ou logs de CI. Crie um token de conta de serviço para automação e faça a rotação quando a equipe mudar.
{% endhint %}
