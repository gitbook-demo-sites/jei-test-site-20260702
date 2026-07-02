---
description: Install and use the official Orbitly JavaScript/TypeScript SDK.
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
