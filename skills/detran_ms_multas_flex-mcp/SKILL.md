---
name: detran_ms_multas_flex-mcp
description: Skill da REST API do DETRAN MS Guia Flex: Multas na MCP.AI: 1 endpoint em /api/detran_ms_multas_flex. DETRAN MS Guia Flex: Multas, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DETRAN MS Guia Flex: Multas — REST API skill

Você tem acesso à **DETRAN MS Guia Flex: Multas** REST API na MCP.AI.

> DETRAN MS Guia Flex: Multas, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/detran_ms_multas_flex
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/detran_ms_multas_flex/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"...","renavam":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/detran_ms_multas_flex/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `detran_ms_multas_flex_consultar`

DETRAN MS Guia Flex: Multas, consulta em fonte oficial. _(POST /api/detran_ms_multas_flex/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `placa` | string | Sim | Parâmetro de consulta "placa". |
| `renavam` | string | Sim | Parâmetro de consulta "renavam". |
| `auto_infracao` | string | Não | Parâmetro de consulta "auto_infracao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_detran_ms_multas_flex` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
