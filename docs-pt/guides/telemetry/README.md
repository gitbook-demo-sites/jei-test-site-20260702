---
description: Entenda a velocidade da sua equipe, o tempo de ciclo e as tendências de entrega.
icon: chart-line
---

# Telemetria

Telemetria é o conjunto de relatórios do Orbitly. Cada projeto recebe um painel; resumos a nível de workspace estão disponíveis nos planos Team e Enterprise.

A telemetria responde a três perguntas operacionais:

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
      <td><i class="fa-gauge-high"></i></td>
      <td><strong>Quanto entregamos?</strong></td>
      <td>Velocidade e combustível concluído por janela de lançamento.</td>
      <td><a href="dashboards.md#velocity">velocidade</a></td>
    </tr>
    <tr>
      <td><i class="fa-stopwatch"></i></td>
      <td><strong>Quanto tempo o trabalho leva?</strong></td>
      <td>Tempo de ciclo desde o início até a conclusão.</td>
      <td><a href="dashboards.md#cycle-time">tempo de ciclo</a></td>
    </tr>
    <tr>
      <td><i class="fa-chart-area"></i></td>
      <td><strong>Onde estão os gargalos?</strong></td>
      <td>Fluxo cumulativo e trabalho envelhecido por coluna.</td>
      <td><a href="dashboards.md#cumulative-flow">fluxo</a></td>
    </tr>
  </tbody>
</table>

## Configuração

{% stepper %}
{% step %}
**Ative a telemetria para o projeto**

Em **Project Settings → Telemetry**, ative a opção. Dados históricos são preenchidos desde a data de criação do projeto.
{% endstep %}

{% step %}
**Mapeie suas colunas de fluxo de trabalho**

Informe ao Orbitly quais colunas significam "trabalho iniciado" e "trabalho concluído" para que o tempo de ciclo seja medido corretamente.
{% endstep %}

{% step %}
**Defina uma linha de base de combustível**

Após 3 janelas de lançamento, o Orbitly calibra automaticamente a velocidade esperada.
{% endstep %}
{% endstepper %}

## Nesta seção

* [Painéis e métricas](dashboards.md)

{% hint style="info" %}
Os dados de telemetria estão disponíveis via API em `GET /telemetry?project={id}` para relatórios personalizados.
{% endhint %}

## Atualização dos dados

As métricas do painel são atualizadas quando o estado da missão muda. Os resumos do workspace são atualizados a cada 15 minutos.

| Fonte dos dados | Comportamento de atualização |
| --------------- | ---------------------------- |
| Status da missão | Quase em tempo real |
| Janelas de lançamento | Quase em tempo real |
| Resumos do workspace | A cada 15 minutos |
| Exportações CSV | Geradas sob demanda |
