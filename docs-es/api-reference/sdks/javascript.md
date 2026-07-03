---
description: "Instala y usa el SDK oficial de Orbitly para JavaScript y TypeScript."
icon: js
---

# SDK de JavaScript

## Instalación

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

## Ejemplo rápido

```typescript
import { Orbitly } from "@orbitly/sdk";

const client = new Orbitly({ token: process.env.ORBITLY_TOKEN });

// Listar misiones abiertas
const missions = await client.missions.list({
  project: "prj_a8x2k",
  status: "open",
});

// Crear una misión
const mission = await client.missions.create({
  project: "prj_a8x2k",
  title: "Agregar conmutador de modo oscuro",
  priority: "medium",
  fuel: 3,
});

console.log(`Creado ${mission.id}`);
```

## Configurar el cliente

{% tabs %}
{% tab title="Token de entorno" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TOKEN,
});
```
{% endtab %}

{% tab title="Espacio de trabajo de prueba" %}
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

## Paginación

Los métodos de listado devuelven iteradores asíncronos — sin manejo manual de cursores:

```typescript
for await (const mission of client.missions.iterate({ project: "prj_a8x2k" })) {
  console.log(mission.title);
}
```

## Manejo de errores

```typescript
import { OrbitlyError, RateLimitError } from "@orbitly/sdk";

try {
  await client.missions.get("ORB-999");
} catch (err) {
  if (err instanceof RateLimitError) {
    // El SDK reintenta automáticamente; esto solo lanza después de 3 intentos
  } else if (err instanceof OrbitlyError) {
    console.error(err.code, err.message);
  }
}
```

{% hint style="info" %}
El SDK reintenta errores de límite de tasa y errores transitorios del servidor. Los errores de validación y permisos se devuelven inmediatamente para que tu aplicación pueda mostrar el problema.
{% endhint %}
