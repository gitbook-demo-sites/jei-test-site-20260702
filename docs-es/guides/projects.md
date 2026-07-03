---
description: "Comprende los bloques fundamentales de Orbitly: proyectos, misiones, ventanas de lanzamiento y telemetría."
icon: diagram-project
---

# Proyectos y Misiones

Todo en Orbitly vive dentro de un proyecto.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody>
<tr>
  <td><h3><i class="fa-folder" style="color:$primary;">:file_folder:</i></h3></td>
  <td><strong>Proyectos</strong></td>
  <td>Agrupa trabajo relacionado por equipo, área de producto o iniciativa del cliente.</td>
  <td><a href="#projects">projects</a></td>
</tr>
<tr>
  <td><h3><i class="fa-list-check" style="color:$primary;">:white_check_mark:</i></h3></td>
  <td><strong>Misiones</strong></td>
  <td>Rastrea unidades individuales de trabajo con estado, responsable, prioridad y combustible.</td>
  <td><a href="#missions">missions</a></td>
</tr>
<tr>
  <td><h3><i class="fa-chart-line" style="color:$primary;">:chart_with_upwards_trend:</i></h3></td>
  <td><strong>Telemetría</strong></td>
  <td>Mide el flujo, la confianza en la entrega y la salud de la ventana de lanzamiento.</td>
  <td><a href="telemetry/README.md">telemetry</a></td>
</tr>
</tbody></table>

## Proyectos

Un proyecto es un contenedor para trabajo relacionado — un área de producto, un compromiso con un cliente o un equipo. Los proyectos tienen:

* Un **tablero** (vista Kanban o de lista)
* Una **línea de tiempo** (vista estilo Gantt de ventanas de lanzamiento)
* **Telemetría** (gráficos e informes)

### Archivado

Los proyectos archivados se vuelven de solo lectura pero permanecen buscables. Restaura en cualquier momento desde **Configuración → Proyectos Archivados**.

## Misiones

Las misiones son unidades individuales de trabajo. Cada misión tiene:

| Campo | Descripción |
| ----- | ----------- |
| Título | Resumen corto del trabajo |
| Estado | Columna en el tablero (p. ej. Backlog, En Progreso, Hecho) |
| Responsable | Un dueño por misión |
| Prioridad | Crítico / Alto / Medio / Bajo |
| Combustible | Estimación de esfuerzo en puntos (1, 2, 3, 5, 8) |
| Etiquetas | Etiquetas libres para filtrar |

### Sub-misiones

Divide misiones grandes en sub-misiones. Una misión padre muestra el progreso agregado:

| Misión | Estado |
| --- | --- |
| `ORB-142` Rediseñar flujo de pago | 70% completado |
| `ORB-143` Nuevo formulario de pago | Hecho |
| `ORB-144` Autocompletado de dirección | Hecho |
| `ORB-145` Revisión de estado de error | En progreso |

### Estados de la misión

Las misiones se mueven a través de las columnas del flujo de trabajo de tu proyecto. Dos estados son especiales:

* **Hecho** — cuenta para la velocidad, activa automatizaciones
* **Depurado** — cancelado; excluido de todas las métricas

> **Consejo:** Usa `Cmd+K` en cualquier parte de la app para saltar a cualquier misión por ID o título.
