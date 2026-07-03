---
description: "Respostas para perguntas comuns sobre configuração, faturamento, missão e solução de problemas do Orbitly."
icon: circle-question
---

# FAQ

## Geral

<details>
<summary>Existe um plano gratuito?</summary>

Sim — o plano **Explorer** é gratuito para sempre: 3 projetos, 5 colegas de equipe, histórico de telemetria de 30 dias.
</details>

<details>
<summary>Posso hospedar o Orbitly por conta própria?</summary>

A auto-hospedagem está disponível no plano Enterprise como uma implantação Docker Compose ou Helm. Contate sales@orbitly.example.com.
</details>

<details>
<summary>Como exporto meus dados?</summary>

**Settings → Workspace → Export** gera um ZIP com exportações JSON e CSV de todos os projetos, missões e comentários. Exportações via API também são suportadas.
</details>

## Faturamento

<details>
<summary>Como funciona a contagem de assentos?</summary>

Admins e Membros contam como assentos. Visualizadores e Convidados são gratuitos em todos os planos.
</details>

<details>
<summary>Posso trocar de plano no meio do ciclo?</summary>

Sim. Upgrades são proporcionais imediatamente; downgrades entram em vigor na próxima renovação.
</details>

## Missões & quadros

<details>
<summary>Uma missão pode ter múltiplos responsáveis?</summary>

Não — um responsável por missão, por design. Use sub-missões para dividir o trabalho entre pessoas.
</details>

<details>
<summary>O que acontece com as missões quando uma janela de lançamento fecha?</summary>

Missões não concluídas são transferidas para o backlog (ou para a próxima janela, se configurado). A estimativa de combustível delas é sinalizada para nova revisão.
</details>

<details>
<summary>Existe um limite de missões?</summary>

Sem limite em qualquer plano pago. Workspaces Explorer são limitados a 500 missões ativas.
</details>

## Solução de problemas

<details>
<summary>Meus PRs do GitHub não estão vinculando às missões</summary>

Verifique se (1) o Orbitly GitHub App tem acesso ao repositório, e (2) o ID da missão aparece no nome da branch ou título do PR exatamente, ex: `ORB-142`, com diferenciação de maiúsculas e minúsculas.
</details>

<details>
<summary>Não estou recebendo notificações do Slack</summary>

Reautorize a integração do Slack em **Settings → Integrations**. Se as notificações pararam após renomear o workspace do Slack, desconecte e reconecte.
</details>
