---
description: "Entenda os blocos de construção principais do Orbitly: projetos, missões, janelas de lançamento e telemetria."
icon: diagram-project
---

# Projetos & Missões

Tudo no Orbitly vive dentro de um projeto.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody>
<tr>
  <td><h3><i class="fa-folder" style="color:$primary;">:file_folder:</i></h3></td>
  <td><strong>Projetos</strong></td>
  <td>Agrupe trabalhos relacionados por equipe, área de produto ou iniciativa do cliente.</td>
  <td><a href="#projects">projects</a></td>
</tr>
<tr>
  <td><h3><i class="fa-list-check" style="color:$primary;">:white_check_mark:</i></h3></td>
  <td><strong>Missões</strong></td>
  <td>Acompanhe unidades individuais de trabalho com status, responsável, prioridade e combustível.</td>
  <td><a href="#missions">missions</a></td>
</tr>
<tr>
  <td><h3><i class="fa-chart-line" style="color:$primary;">:chart_with_upwards_trend:</i></h3></td>
  <td><strong>Telemetria</strong></td>
  <td>Meça fluxo, confiança na entrega e saúde da janela de lançamento.</td>
  <td><a href="telemetry/README.md">telemetry</a></td>
</tr>
</tbody></table>

## Projetos

Um projeto é um contêiner para trabalhos relacionados — uma área de produto, um engajamento com cliente ou uma equipe. Projetos possuem:

* Um **quadro** (visão Kanban ou lista)
* Uma **linha do tempo** (visão estilo Gantt das janelas de lançamento)
* **Telemetria** (gráficos e relatórios)

### Arquivamento

Projetos arquivados tornam-se somente leitura, mas continuam pesquisáveis. Restaure a qualquer momento em **Configurações → Projetos Arquivados**.

## Missões

Missões são unidades individuais de trabalho. Cada missão possui:

| Campo | Descrição |
| ----- | --------- |
| Título | Resumo curto do trabalho |
| Status | Coluna no quadro (ex: Backlog, Em Progresso, Concluído) |
| Responsável | Um dono por missão |
| Prioridade | Crítico / Alto / Médio / Baixo |
| Combustível | Estimativa de esforço em pontos (1, 2, 3, 5, 8) |
| Etiquetas | Tags livres para filtragem |

### Submissões

Divida missões grandes em submissões. Uma missão pai mostra o progresso agregado:

| Missão | Status |
| --- | --- |
| `ORB-142` Redesenhar fluxo de checkout | 70% concluído |
| `ORB-143` Novo formulário de pagamento | Concluído |
| `ORB-144` Autocompletar endereço | Concluído |
| `ORB-145` Revisão do estado de erro | Em progresso |

### Estados da missão

Missões se movem pelas colunas do fluxo de trabalho do seu projeto. Dois estados são especiais:

* **Concluído** — conta para a velocidade, dispara automações
* **Cancelado** — cancelado; excluído de todas as métricas

> **Dica:** Use `Cmd+K` em qualquer lugar do app para pular para qualquer missão pelo ID ou título.
