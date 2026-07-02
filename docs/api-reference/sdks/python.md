---
description: "Install and use the official Orbitly Python SDK for scripts, services, and analytics workflows."
icon: python
---

# Python SDK

## Install

```bash
pip install orbitly
```

## Quick example

```python
from orbitly import Orbitly

client = Orbitly()  # reads ORBITLY_TOKEN from the environment

# List open missions
missions = client.missions.list(project="prj_a8x2k", status="open")

# Create a mission
mission = client.missions.create(
    project="prj_a8x2k",
    title="Add dark mode toggle",
    priority="medium",
    fuel=3,
)
print(f"Created {mission.id}")
```

## Configure the client

{% tabs %}
{% tab title="Environment token" %}
```python
from orbitly import Orbitly

client = Orbitly()  # reads ORBITLY_TOKEN
```
{% endtab %}

{% tab title="Explicit token" %}
```python
from orbitly import Orbitly

client = Orbitly(token="orb_test_xxxxxxxxxxxx")
```
{% endtab %}

{% tab title="Custom base URL" %}
```python
from orbitly import Orbitly

client = Orbitly(
    token="orb_live_xxxxxxxxxxxx",
    base_url="https://api.orbitly.example.com/v2",
)
```
{% endtab %}
{% endtabs %}

## Pagination

```python
for mission in client.missions.iterate(project="prj_a8x2k"):
    print(mission.title)
```

## Async support

```python
from orbitly import AsyncOrbitly

async with AsyncOrbitly() as client:
    me = await client.users.me()
```

## Error handling

```python
from orbitly.errors import OrbitlyError, RateLimitError

try:
    client.missions.get("ORB-999")
except RateLimitError:
    pass  # SDK retries automatically before raising
except OrbitlyError as e:
    print(e.code, e.message)
```

{% hint style="warning" %}
The legacy `orbitly-python` package on PyPI targets API v1 and is unmaintained. Use `orbitly`.
{% endhint %}
