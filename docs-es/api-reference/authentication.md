---
description: "Autentícate en la API de Orbitly con tokens bearer, cuentas de servicio, scopes y límites de tasa."
icon: key
---

# Autenticación

La API de Orbitly utiliza tokens bearer sobre HTTPS.

```text
https://api.orbitly.example.com/v2
```

{% hint style="info" %}
Usa tokens de prueba mientras construyes integraciones. Cambia a tokens en vivo solo después de que el flujo de trabajo esté validado en un espacio de trabajo sandbox.
{% endhint %}

## Tokens de API

Crea tokens en **Settings > API Tokens**.

| Tipo | Prefijo | Uso para |
| ---- | ------- | -------- |
| Live | `orb_live_` | Integraciones en producción |
| Test | `orb_test_` | Espacios de trabajo de desarrollo y sandbox |

Los tokens heredan los permisos del usuario que los creó. Para automatizaciones, crea una **cuenta de servicio** dedicada para que la propiedad no esté ligada a un usuario humano.

## Realizar una solicitud

{% tabs %}
{% tab title="cURL" %}
```bash
curl https://api.orbitly.example.com/v2/missions \
  -H "Authorization: Bearer orb_live_xxxxxxxxxxxx"
```
{% endtab %}

{% tab title="JavaScript" %}
```typescript
const res = await fetch("https://api.orbitly.example.com/v2/missions", {
  headers: {
    Authorization: `Bearer ${process.env.ORBITLY_TOKEN}`,
  },
});
```
{% endtab %}

{% tab title="Python" %}
```python
import os
import requests

res = requests.get(
    "https://api.orbitly.example.com/v2/missions",
    headers={"Authorization": f"Bearer {os.environ['ORBITLY_TOKEN']}"},
)
```
{% endtab %}
{% endtabs %}

## Límites de tasa

| Plan | Solicitudes/min |
| ---- | --------------- |
| Explorer | 60 |
| Team | 300 |
| Enterprise | 1,000 |

El estado del límite de tasa se devuelve en cada respuesta:

```text
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 297
X-RateLimit-Reset: 1782050400
```

Exceder el límite devuelve `429 Too Many Requests` con un encabezado `Retry-After`.

## Seguridad del token

{% stepper %}
{% step %}
## Almacena los tokens en un gestor de secretos

No cometas tokens en el control de versiones ni los pegues en comentarios de issues.
{% endstep %}

{% step %}
## Limita el scope de los tokens

Los espacios de trabajo Enterprise pueden limitar los tokens a proyectos específicos.
{% endstep %}

{% step %}
## Rota los tokens regularmente

Rota los tokens en **Settings > API Tokens > Rotate**, especialmente después de cambios en el equipo o proveedores.
{% endstep %}
{% endstepper %}
