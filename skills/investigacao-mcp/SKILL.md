---
name: investigacao-mcp
description: Skill da REST API do Investigação Cadastral na MCP.AI: 20 endpoints em /api/investigacao. Investigação cadastral de pessoas e empresas: localização (endereço/telefone/email), vínculos e relacionamentos societários, participações, beneficiário final, renda estimada, óbito e propriedade veicular. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Investigação Cadastral — REST API skill

Você tem acesso à **Investigação Cadastral** REST API na MCP.AI.

> Investigação cadastral de pessoas e empresas: localização (endereço/telefone/email), vínculos e relacionamentos societários, participações, beneficiário final, renda estimada, óbito e propriedade veicular. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/investigacao
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
curl -X POST https://api.mcp.ai/api/investigacao/aml \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/investigacao/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (20)

#### `investigacao_aml`

Rede de vínculos societários para prevenção à lavagem de dinheiro, por CPF. _(POST /api/investigacao/aml)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_beneficiario_final`

Beneficiário final (UBO) de uma empresa ou pessoa. _(POST /api/investigacao/beneficiario/final)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_beneficios_sociais`

Benefícios sociais recebidos por um CPF (Bolsa Família, BPC, etc.). _(POST /api/investigacao/beneficios/sociais)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_cnh`

Dados da CNH (Carteira Nacional de Habilitação) por CPF. _(POST /api/investigacao/cnh)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_enriquecimento`

Descobre a pessoa por trás de um celular e/ou email (enriquecimento reverso). _(POST /api/investigacao/enriquecimento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CELULAR` | string | Não | O parâmetro CELULAR pode ser enviado com ou sem formatação. |
| `EMAIL` | string | Não | O parâmetro EMAIL deve possuir formatação válida. |

#### `investigacao_historico_veicular`

Histórico veicular (SP) por CPF ou CNPJ. _(POST /api/investigacao/historico/veicular)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `investigacao_localizacao`

Localização de uma pessoa (nome, endereço, telefone, email). _(POST /api/investigacao/localizacao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. Este parâmetro não é obrigatório, mas caso não utilizado, enviar os parâmetros 'NAME', 'SURNAME' e 'DOB'. |
| `NAME` | string | Não | O parâmetro NAME pode ser enviado com qualquer outro. |
| `SURNAME` | string | Não | O parâmetro SURNAME pode ser enviado com qualquer outro. |
| `DOB` | string | Não | DATA DE NASCIMENTO - Ex: yyyy/MM/dd. |

#### `investigacao_obito`

Verificação de óbito por CPF. _(POST /api/investigacao/obito)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_participacoes`

QSA + participações societárias de um CNPJ (sócios e empresas ligadas). _(POST /api/investigacao/participacoes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `investigacao_pessoa_fisica`

Dados cadastrais completos de um CPF: nome, contato (telefone/email), endereço, renda estimada e faixa salarial. _(POST /api/investigacao/pessoa/fisica)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_pessoa_juridica`

Dados cadastrais completos de um CNPJ. _(POST /api/investigacao/pessoa/juridica)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `investigacao_pis`

PIS vinculado a um CPF. _(POST /api/investigacao/pis)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_prf_infracoes`

Infrações da Polícia Rodoviária Federal por placa + RENAVAM. _(POST /api/investigacao/prf/infracoes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `PLACA` | string | Sim | O parâmetro PLACA pode ser enviado com ou sem formatação. |
| `RENAVAM` | string | Sim | O parâmetro RENAVAM deve ser informado juntamente com seus 11 dígitos numéricos. |
| `TIPO` | string | Sim | O parâmetro TIPO deve ser escolhido. |

#### `investigacao_propriedade_veicular`

Veículos no nome de uma pessoa ou empresa (frota) por CPF/CNPJ. _(POST /api/investigacao/propriedade/veicular)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `investigacao_renda`

Nível socioeconômico e renda estimada de um CPF. _(POST /api/investigacao/renda)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `investigacao_situacao_eleitoral`

Situação eleitoral de uma pessoa (TSE). _(POST /api/investigacao/situacao/eleitoral)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME deve ser enviado de forma completa. Caso informado, enviar também DATANASCIMENTO nestes formatos: dd/mm/aaaa ou dd-mm-aaaa. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `NUMEROTITULOELEITORAL` | string | Não | O parâmetro NUMEROTITULOELEITORAL pode ser enviado com ou sem formatação. |
| `DATANASCIMENTO` | string | Não | O parâmetro DATANASCIMENTO deve ser enviado nestes formatos: dd/mm/aaaa ou dd-mm-aaaa. Caso informado, enviar também NOME de forma completa. |

#### `investigacao_titulo_eleitoral`

Título e local de votação (TSE). _(POST /api/investigacao/titulo/eleitoral)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME deve ser enviado de forma completa. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `NUMEROTITULOELEITORAL` | string | Não | O parâmetro NUMEROTITULOELEITORAL pode ser enviado com ou sem formatação. |
| `DATANASCIMENTO` | string | Sim | O parâmetro DATANASCIMENTO deve ser enviado nestes formatos: dd/mm/aaaa ou dd-mm-aaaa. |
| `NOMEMAE` | string | Sim | O parâmetro NOMEMAE deve ser enviado de forma completa. |

#### `investigacao_veiculo_placa`

Dados e débitos de um veículo pela placa (não exige RENAVAM). _(POST /api/investigacao/veiculo/placa)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `PLACA` | string | Não | O parâmetro PLACA pode ser enviado com ou sem formatação. |

#### `investigacao_vinculo_empregaticio`

Vínculos empregatícios. _(POST /api/investigacao/vinculo/empregaticio)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `investigacao_vinculos_societarios`

Vínculos/relacionamentos societários de uma pessoa ou empresa. _(POST /api/investigacao/vinculos/societarios)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_investigacao` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
