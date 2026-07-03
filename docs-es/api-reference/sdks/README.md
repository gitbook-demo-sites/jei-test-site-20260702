---
description: SDKs oficiales de Orbitly para JavaScript y Python, además de bibliotecas comunitarias.
icon: code
---

# SDKs

Las bibliotecas cliente oficiales envuelven la API REST con modelos tipados, paginación automática, reintentos y manejo de límites de tasa.

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
      <td>Cliente tipado para servicios Node.js, scripts de construcción y herramientas internas.</td>
      <td><a href="javascript.md">javascript</a></td>
    </tr>
    <tr>
      <td><i class="fa-python"></i></td>
      <td><strong>Python</strong></td>
      <td>Cliente Python para pipelines de datos, notebooks y automatización backend.</td>
      <td><a href="python.md">python</a></td>
    </tr>
  </tbody>
</table>

| SDK | Paquete | Versión mínima |
| --- | ------- | -------------- |
| [JavaScript / TypeScript](javascript.md) | `@orbitly/sdk` | Node 18+ |
| [Python](python.md) | `orbitly` | Python 3.10+ |

{% hint style="info" %}
Ambos SDKs se generan a partir de la misma especificación OpenAPI, por lo que los nombres de métodos y modelos coinciden entre los lenguajes.
{% endhint %}

## Bibliotecas comunitarias

No mantenidas por Orbitly, pero usadas activamente:

* `orbitly-go` — cliente Go
* `orbitly-rs` — cliente Rust
* `orbitly-cli-extras` — subcomandos adicionales para CLI

## Versionado

Los SDKs siguen semver y rastrean la API v2. Los cambios incompatibles en la API se lanzan como una nueva versión mayor del SDK con un período de solapamiento de 6 meses.

{% hint style="success" %}
Usa los SDKs para integraciones en producción. Usa ejemplos HTTP en crudo para depurar solicitudes o construir un cliente para un lenguaje no soportado.
{% endhint %}
