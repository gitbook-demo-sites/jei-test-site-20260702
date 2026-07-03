---
description: Comprende la velocidad de tu equipo, el tiempo de ciclo y las tendencias de entrega.
icon: chart-line
---

# Telemetría

La telemetría es el conjunto de informes de Orbitly. Cada proyecto tiene un panel; los resúmenes a nivel de espacio de trabajo están disponibles en los planes Team y Enterprise.

La telemetría responde a tres preguntas operativas:

<table data-view="cards">
  <thead>
    <tr>
      <th width="48"></th>
      <th></th>
      <th></th>
      <th data-hidden data-card-target data-type="content-ref"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><i class="fa-gauge-high"></i></td>
      <td><strong>¿Cuánto entregamos?</strong></td>
      <td>Velocidad y combustible completado por ventana de lanzamiento.</td>
      <td><a href="dashboards.md#velocity">velocidad</a></td>
    </tr>
    <tr>
      <td><i class="fa-stopwatch"></i></td>
      <td><strong>¿Cuánto tarda el trabajo?</strong></td>
      <td>Tiempo de ciclo desde el inicio hasta la finalización.</td>
      <td><a href="dashboards.md#cycle-time">tiempo de ciclo</a></td>
    </tr>
    <tr>
      <td><i class="fa-chart-area"></i></td>
      <td><strong>¿Dónde están los cuellos de botella?</strong></td>
      <td>Flujo acumulativo y trabajo envejecido por columna.</td>
      <td><a href="dashboards.md#cumulative-flow">flujo</a></td>
    </tr>
  </tbody>
</table>

## Configuración

{% stepper %}
{% step %}
**Habilita la telemetría para el proyecto**

En **Project Settings → Telemetry**, actívalo. Los datos históricos se completan desde la fecha de creación del proyecto.
{% endstep %}

{% step %}
**Mapea las columnas de tu flujo de trabajo**

Indica a Orbitly qué columnas significan "trabajo iniciado" y "trabajo terminado" para medir correctamente el tiempo de ciclo.
{% endstep %}

{% step %}
**Establece una línea base de combustible**

Después de 3 ventanas de lanzamiento, Orbitly calibra automáticamente la velocidad esperada.
{% endstep %}
{% endstepper %}

## En esta sección

* [Paneles y métricas](dashboards.md)

{% hint style="info" %}
Los datos de telemetría están disponibles vía API en `GET /telemetry?project={id}` para informes personalizados.
{% endhint %}

## Actualización de datos

Las métricas del panel se actualizan cuando cambia el estado de la misión. Los resúmenes del espacio de trabajo se actualizan cada 15 minutos.

| Fuente de datos | Comportamiento de actualización |
| --------------- | ------------------------------- |
| Estado de la misión | Casi en tiempo real |
| Ventanas de lanzamiento | Casi en tiempo real |
| Resúmenes del espacio de trabajo | Cada 15 minutos |
| Exportaciones CSV | Generadas bajo demanda |
