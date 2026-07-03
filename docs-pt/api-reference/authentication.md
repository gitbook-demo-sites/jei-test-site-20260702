---
description: "Autentique-se na API Orbitly com tokens bearer, contas de serviço, escopos e limites de taxa."
icon: key
---

# Autenticação

A API Orbitly usa tokens bearer via HTTPS.

```text
https://api.orbitly.example.com/v2
```

{% hint style="info" %}
Use tokens de teste enquanto desenvolve integrações. Troque para tokens ao vivo somente após o fluxo de trabalho ser validado em um workspace sandbox.
{% endhint %}

## Tokens da API

Crie tokens em **Configurações > Tokens da API**.

| Tipo | Prefixo | Uso para |
| ---- | ------- | -------- |
| Ao vivo | `orb_live_` | Integrações de produção |
| Teste | `orb_test_` | Workspaces de desenvolvimento e sandbox |

Tokens herdam as permissões do usuário que os criou. Para automações, crie uma **conta de serviço** dedicada para que a propriedade não fique vinculada a um usuário humano.

## Fazer uma requisição

{% tabs %}
{% tab title="cURL" %}
```bash
curl https://api.orbitly.example.com/v2/missions \
  -H "Authorization: Bearer orb_live_xxxxxxxxxxxx"
```
{% endtab %}

{% tab title="JavaScript" %}
```typescript
const res = await fetch("https://api.orbitly.example.com/v2/missions", {
  headers: {
    Authorization: `Bearer ${process.env.ORBITLY_TOKEN}`,
  },
});
```
{% endtab %}

{% tab title="Python" %}
```python
import os
import requests

res = requests.get(
    "https://api.orbitly.example.com/v2/missions",
    headers={"Authorization": f"Bearer {os.environ['ORBITLY_TOKEN']}"},
)
```
{% endtab %}
{% endtabs %}

## Limites de taxa

| Plano | Requisições/min |
| ----- | --------------- |
| Explorer | 60 |
| Team | 300 |
| Enterprise | 1.000 |

O estado do limite de taxa é retornado em toda resposta:

```text
X-RateLimit-Limit: 300
X-RateLimit-Remaining: 297
X-RateLimit-Reset: 1782050400
```

Exceder o limite retorna `429 Too Many Requests` com um cabeçalho `Retry-After`.

## Segurança dos tokens

{% stepper %}
{% step %}
## Armazene tokens em um gerenciador de segredos

Não faça commit de tokens no controle de versão nem cole-os em comentários de issues.
{% endstep %}

{% step %}
## Defina escopos restritos para tokens

Workspaces Enterprise podem restringir tokens a projetos específicos.
{% endstep %}

{% step %}
## Faça a rotação regularmente

Rote tokens em **Configurações > Tokens da API > Rotacionar**, especialmente após mudanças na equipe ou fornecedores.
{% endstep %}
{% endstepper %}
