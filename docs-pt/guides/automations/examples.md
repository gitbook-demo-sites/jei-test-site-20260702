---
description: "Receitas de automação para triagem de bugs, lançamentos, revisões, higiene de sprint e eventos de data warehouse."
icon: wand-magic-sparkles
---

# Receitas de exemplo

Use estas receitas como pontos de partida. Ajuste etiquetas, equipes, canais e templates para corresponder ao seu workspace.

{% hint style="info" %}
Antes de ativar uma receita para todo o projeto, execute-a no modo rascunho e inspecione o histórico de execução para eventos ignorados e correspondentes.
{% endhint %}

## Triagem de bugs

{% tabs %}
{% tab title="Regra" %}
* **Quando:** missão criada
* **Se:** etiqueta contém `bug`
* **Então:** definir prioridade Alta, atribuir em round-robin para a equipe `QA` e postar em `#bug-triage`
{% endtab %}

{% tab title="Mensagem no Slack" %}
```text
Novo bug precisa de triagem: {{mission.id}} - {{mission.title}}
Atribuído a: {{mission.assignee}}
```
{% endtab %}
{% endtabs %}

## Celebrar lançamentos

* **Quando:** missão movida
* **Se:** coluna é `Done` e fuel é maior ou igual a `5`
* **Então:** postar em `#wins`

```text
{{mission.assignee}} entregou {{mission.title}} em {{window.name}}.
```

## Escalar revisões atrasadas

{% stepper %}
{% step %}
## Detectar a revisão atrasada

**Quando** revisão solicitada e nenhuma decisão tomada após 48 horas.
{% endstep %}

{% step %}
## Notificar o responsável

Notifique o gerente do revisor e mencione o dono da missão.
{% endstep %}

{% step %}
## Marcar a missão

Adicione a etiqueta `review-stale` para que apareça na visão de trabalho bloqueado da equipe.
{% endstep %}
{% endstepper %}

## Higiene de sprint

{% tabs %}
{% tab title="Limpeza de rollover" %}
**Quando** janela fechada **então** mover missões não finalizadas para `Backlog`, adicionar etiqueta `rolled-over`, criar missão de acompanhamento "Reestimar missões roladas" atribuída ao líder do projeto.
{% endtab %}

{% tab title="Checklist de kickoff" %}
**Quando** janela aberta **então** criar missões a partir do template `sprint-kickoff`: confirmar capacidade, revisar carry-over, atualizar documento dos stakeholders.
{% endtab %}
{% endtabs %}

## Webhook customizado para data warehouse

**Quando** missão movida **se** coluna é `Done` **então** enviar webhook:

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
Esta receita funciona melhor quando o endpoint receptor aceita rapidamente e processa o evento de forma assíncrona.
{% endhint %}
