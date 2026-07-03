---
description: "Instale e use o SDK oficial Orbitly para JavaScript e TypeScript."
icon: js
---

# SDK JavaScript

## Instalação

{% tabs %}
{% tab title="npm" %}
```bash
npm install @orbitly/sdk
```
{% endtab %}

{% tab title="pnpm" %}
```bash
pnpm add @orbitly/sdk
```
{% endtab %}

{% tab title="yarn" %}
```bash
yarn add @orbitly/sdk
```
{% endtab %}
{% endtabs %}

## Exemplo rápido

```typescript
import { Orbitly } from "@orbitly/sdk";

const client = new Orbitly({ token: process.env.ORBITLY_TOKEN });

// Listar missões abertas
const missions = await client.missions.list({
  project: "prj_a8x2k",
  status: "open",
});

// Criar uma missão
const mission = await client.missions.create({
  project: "prj_a8x2k",
  title: "Adicionar alternância de modo escuro",
  priority: "medium",
  fuel: 3,
});

console.log(`Criado ${mission.id}`);
```

## Configurar o cliente

{% tabs %}
{% tab title="Token de ambiente" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TOKEN,
});
```
{% endtab %}

{% tab title="Workspace de teste" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TEST_TOKEN,
  workspace: "sandbox",
});
```
{% endtab %}

{% tab title="URL base personalizada" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TOKEN,
  baseUrl: "https://api.orbitly.example.com/v2",
});
```
{% endtab %}
{% endtabs %}

## Paginação

Métodos de listagem retornam iteradores assíncronos — sem necessidade de manipulação manual de cursor:

```typescript
for await (const mission of client.missions.iterate({ project: "prj_a8x2k" })) {
  console.log(mission.title);
}
```

## Tratamento de erros

```typescript
import { OrbitlyError, RateLimitError } from "@orbitly/sdk";

try {
  await client.missions.get("ORB-999");
} catch (err) {
  if (err instanceof RateLimitError) {
    // O SDK tenta novamente automaticamente; isso só lança após 3 tentativas
  } else if (err instanceof OrbitlyError) {
    console.error(err.code, err.message);
  }
}
```

{% hint style="info" %}
O SDK tenta novamente em erros de limite de taxa e erros transitórios do servidor. Erros de validação e permissão são retornados imediatamente para que seu app possa exibir o problema.
{% endhint %}
