---
description: "Conecte o Orbitly com Slack, GitHub, Figma, Zapier, APIs e webhooks."
icon: puzzle-piece
---

# Integrações

Conecte o Orbitly às ferramentas que sua equipe já usa. Todas as integrações são gerenciadas em **Configurações > Integrações**.

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
      <td>Crie missões, encaminhe atualizações e mantenha os canais de lançamento informados.</td>
      <td><a href="#slack">slack</a></td>
    </tr>
    <tr>
      <td><i class="fa-github"></i></td>
      <td><strong>GitHub</strong></td>
      <td>Conecte missões a branches, pull requests e releases.</td>
      <td><a href="#github">github</a></td>
    </tr>
    <tr>
      <td><i class="fa-plug"></i></td>
      <td><strong>Webhooks</strong></td>
      <td>Envie eventos em tempo real para sistemas internos e pipelines de dados.</td>
      <td><a href="webhooks.md">webhooks</a></td>
    </tr>
  </tbody>
</table>

## Slack

Use o Slack para manter as conversas do projeto próximas ao trabalho.

* Receba notificações de missões em qualquer canal
* Crie missões pelo Slack com `/orbitly new`
* Expanda links de missões com status ao vivo
* Encaminhe solicitações de revisão para canais do projeto

{% stepper %}
{% step %}
## Conectar Slack

Clique em **Conectar Slack** e autorize seu workspace.
{% endstep %}

{% step %}
## Mapear projetos para canais

Escolha um canal padrão para cada projeto, como `#product-launches` ou `#bug-triage`.
{% endstep %}

{% step %}
## Escolher eventos de notificação

Ative apenas os eventos que o canal deve agir, como missões bloqueadas, lançamentos concluídos ou solicitações de revisão.
{% endstep %}
{% endstepper %}

## GitHub

Vincule a atividade de código ao progresso da missão incluindo o ID da missão, como `ORB-142`, no nome do branch, mensagem de commit ou título do pull request.

| Evento do GitHub | Comportamento no Orbitly |
| ------------ | ---------------- |
| Branch criado | Vincula o branch à missão |
| Pull request aberto | Move a missão para **Em Revisão** |
| Pull request mesclado | Move a missão para **Concluído** se nenhuma revisão obrigatória estiver pendente |
| Pull request fechado | Adiciona um comentário com o motivo do fechamento |

{% hint style="info" %}
Instale o App do Orbitly para GitHub apenas nos repositórios que devem sincronizar o estado do trabalho. Você pode adicionar repositórios depois sem precisar reconectar a integração.
{% endhint %}

## Figma

Cole qualquer link do Figma na descrição de uma missão para incorporar uma miniatura de visualização ao vivo. O Orbitly mantém o link anexado à missão, para que os revisores possam ir diretamente do trabalho de implementação ao contexto do design.

## Zapier

Para fluxos de trabalho sem código, o app Orbitly Zapier expõe gatilhos e ações comuns.

| Gatilhos | Ações |
| -------- | ------- |
| Missão criada | Criar missão |
| Status da missão alterado | Atualizar missão |
| Janela de lançamento fechada | Adicionar comentário |
| Revisão solicitada | Enviar mensagem |

## API e webhooks

Use a REST API e webhooks para integrações personalizadas.

* Comece com [Autenticação](../api-reference/authentication.md) para configuração do token.
* Use [Webhooks](webhooks.md) para entrega de eventos.
* Use [SDKs](../api-reference/sdks/README.md) para bibliotecas cliente tipadas.
