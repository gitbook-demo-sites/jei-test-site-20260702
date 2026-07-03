---
description: "Respuestas a preguntas comunes sobre la configuración, facturación, misiones y solución de problemas de Orbitly."
icon: circle-question
---

# Preguntas frecuentes

## General

<details>
<summary>¿Existe un plan gratuito?</summary>

Sí — el plan **Explorer** es gratuito para siempre: 3 proyectos, 5 compañeros de equipo, historial de telemetría de 30 días.
</details>

<details>
<summary>¿Puedo alojar Orbitly por mi cuenta?</summary>

El autoalojamiento está disponible en el plan Enterprise como una implementación Docker Compose o Helm. Contacta a sales@orbitly.example.com.
</details>

<details>
<summary>¿Cómo exporto mis datos?</summary>

**Settings → Workspace → Export** genera un archivo ZIP con exportaciones JSON y CSV de todos los proyectos, misiones y comentarios. También se soportan exportaciones por API.
</details>

## Facturación

<details>
<summary>¿Cómo funciona el conteo de asientos?</summary>

Los administradores y miembros cuentan como asientos. Los espectadores e invitados son gratuitos en todos los planes.
</details>

<details>
<summary>¿Puedo cambiar de plan a mitad del ciclo?</summary>

Sí. Las actualizaciones se prorratean inmediatamente; las degradaciones se aplican en la siguiente renovación.
</details>

## Misiones y tableros

<details>
<summary>¿Puede una misión tener múltiples asignados?</summary>

No — un propietario por misión, por diseño. Usa sub-misiones para dividir el trabajo entre personas.
</details>

<details>
<summary>¿Qué pasa con las misiones cuando se cierra una ventana de lanzamiento?</summary>

Las misiones no terminadas se trasladan al backlog (o a la siguiente ventana, si está configurado). Su estimación de combustible se marca para una nueva revisión.
</details>

<details>
<summary>¿Hay un límite de misiones?</summary>

No hay límite en ningún plan de pago. Los espacios de trabajo Explorer están limitados a 500 misiones activas.
</details>

## Solución de problemas

<details>
<summary>Mis PRs de GitHub no se vinculan a misiones</summary>

Verifica que (1) la aplicación Orbitly GitHub tenga acceso al repositorio, y (2) el ID de la misión aparezca exactamente en el nombre de la rama o título del PR, por ejemplo `ORB-142`, respetando mayúsculas y minúsculas.
</details>

<details>
<summary>No recibo notificaciones de Slack</summary>

Reautoriza la integración de Slack en **Settings → Integrations**. Si las notificaciones dejaron de funcionar después de renombrar un espacio de trabajo de Slack, desconecta y vuelve a conectar.
</details>
