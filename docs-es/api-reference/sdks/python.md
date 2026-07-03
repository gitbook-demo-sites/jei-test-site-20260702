---
description: "Instala y usa el SDK oficial de Orbitly para Python en scripts, servicios y flujos de trabajo analíticos."
icon: python
---

# SDK de Python

## Instalación

```bash
pip install orbitly
```

## Ejemplo rápido

```python
from orbitly import Orbitly

client = Orbitly()  # lee ORBITLY_TOKEN del entorno

# Listar misiones abiertas
missions = client.missions.list(project="prj_a8x2k", status="open")

# Crear una misión
mission = client.missions.create(
    project="prj_a8x2k",
    title="Agregar conmutador de modo oscuro",
    priority="medium",
    fuel=3,
)
print(f"Creado {mission.id}")
```

## Configurar el cliente

{% tabs %}
{% tab title="Token del entorno" %}
```python
from orbitly import Orbitly

client = Orbitly()  # lee ORBITLY_TOKEN
```
{% endtab %}

{% tab title="Token explícito" %}
```python
from orbitly import Orbitly

client = Orbitly(token="orb_test_xxxxxxxxxxxx")
```
{% endtab %}

{% tab title="URL base personalizada" %}
```python
from orbitly import Orbitly

client = Orbitly(
    token="orb_live_xxxxxxxxxxxx",
    base_url="https://api.orbitly.example.com/v2",
)
```
{% endtab %}
{% endtabs %}

## Paginación

```python
for mission in client.missions.iterate(project="prj_a8x2k"):
    print(mission.title)
```

## Soporte asíncrono

```python
from orbitly import AsyncOrbitly

async with AsyncOrbitly() as client:
    me = await client.users.me()
```

## Manejo de errores

```python
from orbitly.errors import OrbitlyError, RateLimitError

try:
    client.missions.get("ORB-999")
except RateLimitError:
    pass  # El SDK reintenta automáticamente antes de lanzar
except OrbitlyError as e:
    print(e.code, e.message)
```

{% hint style="warning" %}
El paquete legado `orbitly-python` en PyPI apunta a la API v1 y no está mantenido. Usa `orbitly`.
{% endhint %}
