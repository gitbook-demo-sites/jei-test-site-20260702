---
description: "Atualizações do produto, mudanças na API, correções e desativações."
icon: clock-rotate-left
layout:
  width: wide
---

# Registro de alterações

{% updates format="full" %}
{% update date="2026-06-15" tags="product,fix" %}
## v3.2

* Dependências de missões agora podem marcar missões como bloqueadas por outros trabalhos e visualizar bloqueadores na linha do tempo.
* Importação CSV está disponível para criação em massa de missões.
* A renderização do quadro está cerca de 40% mais rápida em projetos com mais de 200 missões.
* A transferência da janela de lançamento não duplica mais sub-missões em casos extremos.
{% endupdate %}

{% update date="2026-04-10" tags="product,api" %}
## v3.1

* Embeds do Figma são suportados nas descrições das missões.
* A CLI agora inclui `orbitly window close`.
* A busca corresponde ao conteúdo dos comentários, não apenas aos títulos das missões.
* O tratamento do fuso horário no resumo diário é mais confiável para deslocamentos UTC+.
{% endupdate %}

{% update date="2026-02-18" tags="product,api,breaking" %}
## v3.0

* Telemetria 2.0 adiciona tendências de velocidade, tempo de ciclo e dashboards de fluxo cumulativo.
* Contas de serviço estão disponíveis para automações via API.
* Papéis de convidado suportam colaboradores externos.
* A API v1 está descontinuada e programada para desativação em dezembro de 2026. Migre para `/v2`.
{% endupdate %}

{% update date="2025-12-08" tags="product,fix" %}
## v2.9

* Integração com Zapier está agora disponível.
* A política de reintento de webhook agora limita a cinco tentativas com backoff.
* Autocompletar `@menção` funciona para nomes com diacríticos.
{% endupdate %}
{% endupdates %}
