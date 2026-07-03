---
description: "Instale e use o SDK oficial Orbitly Python para scripts, serviços e fluxos de trabalho analíticos."
icon: python
---

# SDK Python

## Instalação

```bash
pip install orbitly
```

## Exemplo rápido

```python
from orbitly import Orbitly

client = Orbitly()  # lê ORBITLY_TOKEN do ambiente

# Listar missões abertas
missions = client.missions.list(project="prj_a8x2k", status="open")

# Criar uma missão
mission = client.missions.create(
    project="prj_a8x2k",
    title="Adicionar alternância de modo escuro",
    priority="medium",
    fuel=3,
)
print(f"Criado {mission.id}")
```

## Configurar o cliente

{% tabs %}
{% tab title="Token do ambiente" %}
```python
from orbitly import Orbitly

client = Orbitly()  # lê ORBITLY_TOKEN
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

## Paginação

```python
for mission in client.missions.iterate(project="prj_a8x2k"):
    print(mission.title)
```

## Suporte assíncrono

```python
from orbitly import AsyncOrbitly

async with AsyncOrbitly() as client:
    me = await client.users.me()
```

## Tratamento de erros

```python
from orbitly.errors import OrbitlyError, RateLimitError

try:
    client.missions.get("ORB-999")
except RateLimitError:
    pass  # SDK tenta novamente automaticamente antes de lançar
except OrbitlyError as e:
    print(e.code, e.message)
```

{% hint style="warning" %}
O pacote legado `orbitly-python` no PyPI é direcionado para a API v1 e não é mantido. Use `orbitly`.
{% endhint %}
