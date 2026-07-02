---
description: "Install and use the official Orbitly JavaScript and TypeScript SDK."
icon: js
---

# JavaScript SDK

## Install

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

## Quick example

```typescript
import { Orbitly } from "@orbitly/sdk";

const client = new Orbitly({ token: process.env.ORBITLY_TOKEN });

// List open missions
const missions = await client.missions.list({
  project: "prj_a8x2k",
  status: "open",
});

// Create a mission
const mission = await client.missions.create({
  project: "prj_a8x2k",
  title: "Add dark mode toggle",
  priority: "medium",
  fuel: 3,
});

console.log(`Created ${mission.id}`);
```

## Configure the client

{% tabs %}
{% tab title="Environment token" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TOKEN,
});
```
{% endtab %}

{% tab title="Test workspace" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TEST_TOKEN,
  workspace: "sandbox",
});
```
{% endtab %}

{% tab title="Custom base URL" %}
```typescript
const client = new Orbitly({
  token: process.env.ORBITLY_TOKEN,
  baseUrl: "https://api.orbitly.example.com/v2",
});
```
{% endtab %}
{% endtabs %}

## Pagination

List methods return async iterators — no manual cursor handling:

```typescript
for await (const mission of client.missions.iterate({ project: "prj_a8x2k" })) {
  console.log(mission.title);
}
```

## Error handling

```typescript
import { OrbitlyError, RateLimitError } from "@orbitly/sdk";

try {
  await client.missions.get("ORB-999");
} catch (err) {
  if (err instanceof RateLimitError) {
    // SDK retries automatically; this only throws after 3 attempts
  } else if (err instanceof OrbitlyError) {
    console.error(err.code, err.message);
  }
}
```

{% hint style="info" %}
The SDK retries rate-limited and transient server errors. Validation and permission errors are returned immediately so your app can surface the problem.
{% endhint %}
