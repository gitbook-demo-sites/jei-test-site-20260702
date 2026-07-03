---
description: SDKs oficiais da Orbitly para JavaScript e Python, além de bibliotecas da comunidade.
icon: code
---

# SDKs

As bibliotecas clientes oficiais encapsulam a API REST com modelos tipados, paginação automática, tentativas e controle de limite de taxa.

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
      <td><i class="fa-js"></i></td>
      <td><strong>JavaScript / TypeScript</strong></td>
      <td>Cliente tipado para serviços Node.js, scripts de build e ferramentas internas.</td>
      <td><a href="javascript.md">javascript</a></td>
    </tr>
    <tr>
      <td><i class="fa-python"></i></td>
      <td><strong>Python</strong></td>
      <td>Cliente Python para pipelines de dados, notebooks e automação backend.</td>
      <td><a href="python.md">python</a></td>
    </tr>
  </tbody>
</table>

| SDK | Pacote | Versão mínima |
| --- | ------- | ----------- |
| [JavaScript / TypeScript](javascript.md) | `@orbitly/sdk` | Node 18+ |
| [Python](python.md) | `orbitly` | Python 3.10+ |

{% hint style="info" %}
Ambos os SDKs são gerados a partir da mesma especificação OpenAPI, portanto os nomes dos métodos e modelos correspondem entre as linguagens.
{% endhint %}

## Bibliotecas da comunidade

Não mantidas pela Orbitly, mas usadas ativamente:

* `orbitly-go` — cliente Go
* `orbitly-rs` — cliente Rust
* `orbitly-cli-extras` — subcomandos extras para CLI

## Versionamento

Os SDKs seguem semver e acompanham a API v2. Mudanças incompatíveis na API são lançadas como uma nova versão major do SDK com um período de sobreposição de 6 meses.

{% hint style="success" %}
Use os SDKs para integrações em produção. Use exemplos HTTP puros ao depurar requisições ou construir um cliente para uma linguagem não suportada.
{% endhint %}
