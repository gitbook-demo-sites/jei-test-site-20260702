---
description: "Cada gráfico no painel de Telemetria, explicado com faixas saudáveis e opções de exportação."
icon: chart-simple
layout:
  width: wide
---

# Painéis & métricas

Os painéis de telemetria são projetados para revisões operacionais semanais. Use os gráficos juntos: a velocidade mostra o que foi entregue, o tempo de ciclo indica quanto tempo levou, e o fluxo cumulativo revela onde o trabalho está travado.

## Velocidade

Total de combustível concluído por janela de lançamento, com uma média móvel de 3 janelas. Missões descartadas são excluídas.

{% hint style="success" %}
Uma média móvel estável é mais útil do que uma única janela de lançamento heroica. Procure por rendimento repetível.
{% endhint %}

## Burndown

Combustível restante na janela atual, dia a dia, contra uma linha ideal. Finais de semana são excluídos se sua semana de trabalho estiver configurada (veja [Configuração](../../getting-started/configuration.md)).

## Tempo de ciclo

Tempo desde **Em Progresso** até **Concluído**, mostrado como um gráfico de dispersão com faixas p50/p85.

| Percentil | Faixa saudável |
| ---------- | -------------- |
| p50 | 3 dias ou menos |
| p85 | 7 dias ou menos |

## Fluxo cumulativo

Gráfico de área empilhada da contagem de missões por coluna ao longo do tempo. Faixas que se alargam indicam gargalos.

```mermaid
flowchart LR
    Backlog --> Ready
    Ready --> Progress["Em Progresso"]
    Progress --> Review
    Review --> Done
```

<details>
<summary>Como interpretar uma faixa que se alarga</summary>

Se a faixa **Em Revisão** cresce por vários dias enquanto **Concluído** permanece estável, os revisores provavelmente são o gargalo. Adicione capacidade de revisão, divida missões grandes ou use uma automação para escalar revisões estagnadas.
</details>

## Exportação

Cada gráfico pode ser exportado como PNG ou CSV. Painéis podem ser compartilhados com um link público somente leitura em planos Enterprise.

{% hint style="warning" %}
Alterar os mapeamentos das colunas do fluxo de trabalho recalcula todas as métricas históricas. Espere que os painéis mudem após o remapeamento.
{% endhint %}
