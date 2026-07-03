---
description: "Conecta Orbitly con Slack, GitHub, Figma, Zapier, APIs y webhooks."
icon: puzzle-piece
---

# Integraciones

Conecta Orbitly con las herramientas que tu equipo ya usa. Todas las integraciones se gestionan en **Configuración > Integraciones**.

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
      <td><i class="fa-slack"></i></td>
      <td><strong>Slack</strong></td>
      <td>Crea misiones, enruta actualizaciones y mantiene informados los canales de lanzamiento.</td>
      <td><a href="#slack">slack</a></td>
    </tr>
    <tr>
      <td><i class="fa-github"></i></td>
      <td><strong>GitHub</strong></td>
      <td>Conecta misiones con ramas, pull requests y lanzamientos.</td>
      <td><a href="#github">github</a></td>
    </tr>
    <tr>
      <td><i class="fa-plug"></i></td>
      <td><strong>Webhooks</strong></td>
      <td>Envía eventos en tiempo real a sistemas internos y pipelines de datos.</td>
      <td><a href="webhooks.md">webhooks</a></td>
    </tr>
  </tbody>
</table>

## Slack

Usa Slack para mantener las conversaciones del proyecto cerca del trabajo.

* Recibe notificaciones de misiones en cualquier canal
* Crea misiones desde Slack con `/orbitly new`
* Despliega enlaces de misiones con estado en vivo
* Enruta solicitudes de revisión a canales de proyecto

{% stepper %}
{% step %}
## Conectar Slack

Haz clic en **Conectar Slack** y autoriza tu espacio de trabajo.
{% endstep %}

{% step %}
## Asignar proyectos a canales

Elige un canal predeterminado por proyecto, como `#product-launches` o `#bug-triage`.
{% endstep %}

{% step %}
## Elegir eventos de notificación

Activa solo los eventos sobre los que el canal debe actuar, como misiones bloqueadas, lanzamientos completados o solicitudes de revisión.
{% endstep %}
{% endstepper %}

## GitHub

Vincula la actividad de código con el progreso de la misión incluyendo el ID de la misión, como `ORB-142`, en el nombre de una rama, mensaje de commit o título de pull request.

| Evento de GitHub | Comportamiento en Orbitly |
| ---------------- | ------------------------- |
| Rama creada | Vincula la rama a la misión |
| Pull request abierto | Mueve la misión a **En Revisión** |
| Pull request fusionado | Mueve la misión a **Hecho** si no hay revisiones requeridas pendientes |
| Pull request cerrado | Añade un comentario con la razón del cierre |

{% hint style="info" %}
Instala la App de Orbitly para GitHub solo en los repositorios que deben sincronizar el estado del trabajo. Puedes agregar repositorios después sin necesidad de reconectar la integración.
{% endhint %}

## Figma

Pega cualquier enlace de Figma en la descripción de una misión para incrustar una miniatura de vista previa en vivo. Orbitly mantiene el enlace adjunto a la misión, para que los revisores puedan saltar directamente del trabajo de implementación al contexto de diseño.

## Zapier

Para flujos de trabajo sin código, la app Orbitly Zapier expone disparadores y acciones comunes.

| Disparadores | Acciones |
| ------------ | -------- |
| Misión creada | Crear misión |
| Estado de misión cambiado | Actualizar misión |
| Ventana de lanzamiento cerrada | Añadir comentario |
| Revisión solicitada | Enviar mensaje |

## API y webhooks

Usa la API REST y webhooks para integraciones personalizadas.

* Comienza con [Autenticación](../api-reference/authentication.md) para la configuración del token.
* Usa [Webhooks](webhooks.md) para la entrega de eventos.
* Usa [SDKs](../api-reference/sdks/README.md) para librerías cliente tipadas.
