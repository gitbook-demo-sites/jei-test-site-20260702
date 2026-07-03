---
description: "Endpoints REST principales para proyectos, misiones, ventanas de lanzamiento y usuarios."
icon: code
---

# Endpoints

Todos los endpoints son relativos a `https://api.orbitly.example.com/v2`. Las respuestas son JSON. Los endpoints de lista soportan `?limit=` (máximo 100) y paginación basada en cursor mediante `?after=`.

{% hint style="info" %}
Usa la API para automatización, importaciones, reportes e integraciones de flujo de trabajo. Usa webhooks cuando otro sistema necesite reaccionar a cambios en Orbitly.
{% endhint %}

## Misiones

### Listar misiones

{% tabs %}
{% tab title="Solicitud" %}
```
GET /missions?project=prj_a8x2k&status=open
```
{% endtab %}

{% tab title="Respuesta" %}
```json
{
  "data": [
    {
      "id": "ORB-142",
      "title": "Rediseñar flujo de pago",
      "status": "in_progress",
      "assignee": "usr_8f3ka92",
      "priority": "high",
      "fuel": 5,
      "created_at": "2026-06-12T09:14:00Z"
    }
  ],
  "next_cursor": "eyJpZCI6MTQyfQ"
}
```
{% endtab %}
{% endtabs %}

### Crear una misión

```
POST /missions
```

```json
{
  "project": "prj_a8x2k",
  "title": "Agregar conmutador de modo oscuro",
  "priority": "medium",
  "fuel": 3
}
```

### Actualizar una misión

```
PATCH /missions/ORB-142
```

Cualquier campo del objeto misión puede ser actualizado. Los cambios de estado activan webhooks.

## Proyectos

| Método | Ruta | Descripción |
| ------ | ---- | ----------- |
| `GET` | `/projects` | Listar proyectos |
| `POST` | `/projects` | Crear un proyecto |
| `GET` | `/projects/{id}` | Obtener detalles del proyecto |
| `DELETE` | `/projects/{id}` | Archivar un proyecto |

## Ventanas de lanzamiento

| Método | Ruta | Descripción |
| ------ | ---- | ----------- |
| `GET` | `/windows?project={id}` | Listar ventanas de lanzamiento |
| `POST` | `/windows` | Crear una ventana de lanzamiento |
| `POST` | `/windows/{id}/close` | Cerrar una ventana anticipadamente |

## Usuarios

| Método | Ruta | Descripción |
| ------ | ---- | ----------- |
| `GET` | `/users/me` | Usuario autenticado actual |
| `GET` | `/users?workspace={slug}` | Listar miembros del espacio de trabajo |
