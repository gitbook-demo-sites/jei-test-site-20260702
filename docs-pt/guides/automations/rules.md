---
description: "Referência completa para gatilhos de automação, condições, ações e histórico de execução."
icon: list-check
---

# Regras & gatilhos

As regras são avaliadas sempre que seu evento gatilho ocorre. Se todas as condições forem atendidas, o Orbitly executa as ações configuradas na ordem.

## Gatilhos

| Gatilho | Dispara quando |
| ------- | -------------- |
| Missão criada | Qualquer nova missão no projeto |
| Missão movida | Uma missão muda de coluna |
| Responsável alterado | Transferência de propriedade |
| Fuel alterado | A estimativa é atualizada |
| Janela aberta / fechada | Uma janela de lançamento começa ou termina |
| Decisão de revisão | Um revisor aprova ou solicita alterações |

{% hint style="info" %}
Use o gatilho mais específico disponível. Gatilhos amplos são poderosos, mas têm maior chance de disparar em excesso.
{% endhint %}

## Condições

Condições filtram quais eventos realmente executam as ações. Combine com E/OU:

* Coluna **é / não é** uma coluna específica
* Label **contém / não contém**
* Prioridade **é pelo menos** (Crítico > Alto > Médio > Baixo)
* Responsável **é / está na equipe**
* Fuel **maior / menor que**

## Ações

As ações são executadas de cima para baixo. Se uma ação falhar, as ações restantes são ignoradas e a execução é marcada como falha no histórico.

{% tabs %}
{% tab title="Atualizações no quadro" %}
* Mover missão para uma coluna
* Definir prioridade, label ou fuel
* Atribuir a uma pessoa ou em rodízio dentro de uma equipe
* Criar uma missão de acompanhamento a partir de um template
{% endtab %}

{% tab title="Notificações" %}
* Postar em um canal do Slack
* Enviar uma notificação direta
* Adicionar um comentário na missão
* Solicitar revisão de uma equipe
{% endtab %}

{% tab title="Integrações" %}
* Enviar um webhook
* Adicionar um comentário de status no GitHub
* Exportar um payload para um destino de relatório
{% endtab %}
{% endtabs %}

## Variáveis

Os payloads das ações suportam variáveis:

| Variável | Valor de exemplo |
| -------- | ---------------- |
| `{{mission.id}}` | `ORB-142` |
| `{{mission.title}}` | `Redesign checkout flow` |
| `{{mission.assignee}}` | `sam@example.com` |
| `{{window.name}}` | `July Launch Window` |

{% hint style="info" %}
As variáveis são resolvidas no momento da execução. Se um campo estiver vazio, o Orbitly deixa a variável em branco ao invés de falhar na regra.
{% endhint %}

## Registro de execução

Cada regra mantém um registro de execução de 30 dias em **Automations → History**, incluindo execuções puladas (condição não atendida) e falhas com detalhes do erro.

<details>
<summary>Padrão recomendado para nomes</summary>

Use nomes que descrevam o gatilho e o resultado:

* `Quando bug é criado, atribuir QA`
* `Quando revisão está desatualizada, notificar gerente`
* `Quando missão grande é concluída, postar nas vitórias`

Evite nomes genéricos como `Automação Slack` ou `Regra 1`.
</details>
