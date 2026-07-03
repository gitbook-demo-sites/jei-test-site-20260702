---
description: "Referencia completa para disparadores, condiciones, acciones y historial de ejecución de automatizaciones."
icon: list-check
---

# Reglas y disparadores

Las reglas se evalúan cada vez que ocurre su evento disparador. Si todas las condiciones se cumplen, Orbitly ejecuta las acciones configuradas en orden.

## Disparadores

| Disparador | Se activa cuando |
| ---------- | ---------------- |
| Misión creada | Cualquier misión nueva en el proyecto |
| Misión movida | Una misión cambia de columna |
| Cambió el asignado | Se transfiere la propiedad |
| Cambió el fuel | Se actualiza la estimación |
| Ventana abierta / cerrada | Una ventana de lanzamiento comienza o termina |
| Decisión de revisión | Un revisor aprueba o solicita cambios |

{% hint style="info" %}
Usa el disparador más específico disponible. Los disparadores amplios son poderosos, pero es más fácil que se activen en exceso.
{% endhint %}

## Condiciones

Las condiciones filtran qué eventos realmente ejecutan las acciones. Combina con AND/OR:

* Columna **es / no es** una columna específica
* Etiqueta **contiene / no contiene**
* Prioridad **es al menos** (Crítica > Alta > Media > Baja)
* Asignado **es / está en equipo**
* Fuel **mayor / menor que**

## Acciones

Las acciones se ejecutan de arriba hacia abajo. Si una acción falla, las acciones restantes se omiten y la ejecución se marca como fallida en el historial.

{% tabs %}
{% tab title="Actualizaciones del tablero" %}
* Mover misión a una columna
* Establecer prioridad, etiqueta o fuel
* Asignar a una persona o en ronda dentro de un equipo
* Crear una misión de seguimiento desde una plantilla
{% endtab %}

{% tab title="Notificaciones" %}
* Publicar en un canal de Slack
* Enviar una notificación directa
* Agregar un comentario a la misión
* Solicitar revisión a un equipo
{% endtab %}

{% tab title="Integraciones" %}
* Enviar un webhook
* Agregar un comentario de estado en GitHub
* Exportar una carga útil a un destino de reportes
{% endtab %}
{% endtabs %}

## Variables

Las cargas útiles de las acciones soportan variables:

| Variable | Valor de ejemplo |
| -------- | ---------------- |
| `{{mission.id}}` | `ORB-142` |
| `{{mission.title}}` | `Rediseñar flujo de pago` |
| `{{mission.assignee}}` | `sam@example.com` |
| `{{window.name}}` | `Ventana de lanzamiento de julio` |

{% hint style="info" %}
Las variables se resuelven en tiempo de ejecución. Si un campo está vacío, Orbitly deja la variable en blanco en lugar de fallar la regla.
{% endhint %}

## Registro de ejecución

Cada regla mantiene un registro de ejecución de 30 días bajo **Automatizaciones → Historial**, incluyendo ejecuciones omitidas (condición no cumplida) y fallos con detalles del error.

<details>
<summary>Patrón de nombres recomendado</summary>

Usa nombres que describan el disparador y el resultado:

* `Cuando se crea un bug, asignar QA`
* `Cuando la revisión está obsoleta, notificar al gerente`
* `Cuando se envía una misión grande, publicar en wins`

Evita nombres genéricos como `Automatización Slack` o `Regla 1`.
</details>
