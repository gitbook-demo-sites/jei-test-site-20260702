---
description: "Endpoints REST principais para projetos, missões, janelas de lançamento e usuários."
icon: code
---

# Endpoints

Todos os endpoints são relativos a `https://api.orbitly.example.com/v2`. As respostas são em JSON. Endpoints de listagem suportam `?limit=` (máximo 100) e paginação baseada em cursor via `?after=`.

{% hint style="info" %}
Use a API para automação, importações, relatórios e integrações de fluxo de trabalho. Use webhooks quando outro sistema precisar reagir a mudanças no Orbitly.
{% endhint %}

## Missões

### Listar missões

{% tabs %}
{% tab title="Requisição" %}
```
GET /missions?project=prj_a8x2k&status=open
```
{% endtab %}

{% tab title="Resposta" %}
```json
{
  "data": [
    {
      "id": "ORB-142",
      "title": "Redesign checkout flow",
      "status": "in_progress",
      "assignee": "usr_8f3ka92",
      "priority": "high",
      "fuel": 5,
      "created_at": "2026-06-12T09:14:00Z"
    }
  ],
  "next_cursor": "eyJpZCI6MTQyfQ"
}
```
{% endtab %}
{% endtabs %}

### Criar uma missão

```
POST /missions
```

```json
{
  "project": "prj_a8x2k",
  "title": "Add dark mode toggle",
  "priority": "medium",
  "fuel": 3
}
```

### Atualizar uma missão

```
PATCH /missions/ORB-142
```

Qualquer campo do objeto missão pode ser atualizado. Mudanças de status disparam webhooks.

## Projetos

| Método | Caminho | Descrição |
| ------ | ------- | --------- |
| `GET` | `/projects` | Listar projetos |
| `POST` | `/projects` | Criar um projeto |
| `GET` | `/projects/{id}` | Obter detalhes do projeto |
| `DELETE` | `/projects/{id}` | Arquivar um projeto |

## Janelas de lançamento

| Método | Caminho | Descrição |
| ------ | ------- | --------- |
| `GET` | `/windows?project={id}` | Listar janelas de lançamento |
| `POST` | `/windows` | Criar uma janela de lançamento |
| `POST` | `/windows/{id}/close` | Fechar uma janela antecipadamente |

## Usuários

| Método | Caminho | Descrição |
| ------ | ------- | --------- |
| `GET` | `/users/me` | Usuário autenticado atual |
| `GET` | `/users?workspace={slug}` | Listar membros do workspace |
