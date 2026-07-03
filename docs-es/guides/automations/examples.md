---
description: "Recetas de automatización para copiar y pegar en la clasificación de errores, lanzamientos, revisiones, higiene de sprint y eventos de almacén."
icon: wand-magic-sparkles
---

# Recetas de ejemplo

Usa estas recetas como puntos de partida. Ajusta etiquetas, equipos, canales y plantillas para que coincidan con tu espacio de trabajo.

{% hint style="info" %}
Antes de habilitar una receta para todo el proyecto, ejecútala en modo borrador e inspecciona el historial de ejecución para eventos omitidos y coincidentes.
{% endhint %}

## Clasificación de errores

{% tabs %}
{% tab title="Regla" %}
* **Cuando:** misión creada
* **Si:** la etiqueta contiene `bug`
* **Entonces:** establecer prioridad Alta, asignar por turno al equipo `QA` y publicar en `#bug-triage`
{% endtab %}

{% tab title="Mensaje de Slack" %}
```text
Nuevo error necesita clasificación: {{mission.id}} - {{mission.title}}
Asignado a: {{mission.assignee}}
```
{% endtab %}
{% endtabs %}

## Celebrar lanzamientos

* **Cuando:** misión movida
* **Si:** la columna es `Done` y el fuel es mayor o igual a `5`
* **Entonces:** publicar en `#wins`

```text
{{mission.assignee}} entregó {{mission.title}} en {{window.name}}.
```

## Escalar revisiones obsoletas

{% stepper %}
{% step %}
## Detectar la revisión obsoleta

**Cuando** se solicita revisión y no se toma una decisión después de 48 horas.
{% endstep %}

{% step %}
## Notificar al propietario

Notificar al gerente del revisor y mencionar al propietario de la misión.
{% endstep %}

{% step %}
## Marcar la misión

Agregar la etiqueta `review-stale` para que aparezca en la vista de trabajo bloqueado del equipo.
{% endstep %}
{% endstepper %}

## Higiene de sprint

{% tabs %}
{% tab title="Limpieza de rollover" %}
**Cuando** se cierra la ventana **entonces** mover misiones sin terminar a `Backlog`, agregar etiqueta `rolled-over`, crear misión de seguimiento "Re-estimar misiones transferidas" asignada al líder del proyecto.
{% endtab %}

{% tab title="Lista de verificación de inicio" %}
**Cuando** se abre la ventana **entonces** crear misiones desde la plantilla `sprint-kickoff`: confirmar capacidad, revisar arrastre, actualizar documento de interesados.
{% endtab %}
{% endtabs %}

## Webhook personalizado a un data warehouse

**Cuando** misión movida **si** la columna es `Done` **entonces** enviar webhook:

```json
{
  "event": "shipped",
  "id": "{{mission.id}}",
  "title": "{{mission.title}}",
  "fuel": "{{mission.fuel}}",
  "window": "{{window.name}}"
}
```

{% hint style="success" %}
Esta receta funciona mejor cuando el endpoint receptor acepta rápidamente y procesa el evento de forma asíncrona.
{% endhint %}
