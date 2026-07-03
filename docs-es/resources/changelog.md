---
description: "Actualizaciones del producto, cambios en la API, correcciones y desaprobaciones."
icon: clock-rotate-left
layout:
  width: wide
---

# Registro de cambios

{% updates format="full" %}
{% update date="2026-06-15" tags="product,fix" %}
## v3.2

* Las dependencias de misiones ahora pueden marcar misiones como bloqueadas por otros trabajos y visualizar los bloqueadores en la línea de tiempo.
* La importación CSV está disponible para la creación masiva de misiones.
* La renderización del tablero es aproximadamente un 40% más rápida en proyectos con más de 200 misiones.
* El rollover de la ventana de lanzamiento ya no duplica submisiones en casos límite.
{% endupdate %}

{% update date="2026-04-10" tags="product,api" %}
## v3.1

* Se soportan incrustaciones de Figma en las descripciones de misiones.
* La CLI ahora incluye `orbitly window close`.
* La búsqueda coincide con el contenido de los comentarios, no solo con los títulos de las misiones.
* El manejo de la zona horaria en el resumen diario es más fiable para desplazamientos UTC+.
{% endupdate %}

{% update date="2026-02-18" tags="product,api,breaking" %}
## v3.0

* Telemetría 2.0 añade tendencias de velocidad, tiempo de ciclo y paneles de flujo acumulativo.
* Las cuentas de servicio están disponibles para automatizaciones de API.
* Los roles de invitado soportan colaboradores externos.
* La API v1 está desaprobada y programada para su retirada en diciembre de 2026. Migra a `/v2`.
{% endupdate %}

{% update date="2025-12-08" tags="product,fix" %}
## v2.9

* La integración con Zapier ya está disponible.
* La política de reintentos de webhook ahora se limita a cinco intentos con retroceso.
* El autocompletado de `@mención` funciona para nombres con diacríticos.
{% endupdate %}
{% endupdates %}
