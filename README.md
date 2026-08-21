# Investigação Cadastral

### Investigação Cadastral para Claude, ChatGPT e agentes de IA

Investigação cadastral de pessoas e empresas: localização (endereço/telefone/email), vínculos e relacionamentos societários, participações, beneficiário final, renda estimada, óbito e propriedade veicular. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

- 📊 **20 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Investigação Cadastral` e **URL** `https://api.mcp.ai/p_investigacao`.

### Cursor

[➕ Instalar Investigação Cadastral no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=investigacao&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9pbnZlc3RpZ2FjYW8ifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Investigação Cadastral no VS Code](vscode:mcp/install?name=investigacao&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_investigacao%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_investigacao
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Localize a pessoa do CPF 000.000.000-00 (endereço e telefone)
Quais empresas o CNPJ X tem vínculo societário?
Quem é o beneficiário final dessa empresa?
```

---

## 20 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `investigacao_pessoa_fisica` | Dados cadastrais completos de um CPF: nome, contato (telefone/email), endereço, renda estimada e faixa salarial. |
| `investigacao_pessoa_juridica` | Dados cadastrais completos de um CNPJ. |
| `investigacao_localizacao` | Localização de uma pessoa (nome, endereço, telefone, email). |
| `investigacao_enriquecimento` | Descobre a pessoa por trás de um celular e/ou email (enriquecimento reverso). |
| `investigacao_vinculos_societarios` | Vínculos/relacionamentos societários de uma pessoa ou empresa. |
| `investigacao_participacoes` | QSA + participações societárias de um CNPJ (sócios e empresas ligadas). |
| `investigacao_beneficiario_final` | Beneficiário final (UBO) de uma empresa ou pessoa. |
| `investigacao_aml` | Rede de vínculos societários para prevenção à lavagem de dinheiro, por CPF. |
| `investigacao_renda` | Nível socioeconômico e renda estimada de um CPF. |
| `investigacao_vinculo_empregaticio` | Vínculos empregatícios. |
| `investigacao_obito` | Verificação de óbito por CPF. |
| `investigacao_propriedade_veicular` | Veículos no nome de uma pessoa ou empresa (frota) por CPF/CNPJ. |
| `investigacao_pis` | PIS vinculado a um CPF. |
| `investigacao_veiculo_placa` | Dados e débitos de um veículo pela placa (não exige RENAVAM). |
| `investigacao_cnh` | Dados da CNH (Carteira Nacional de Habilitação) por CPF. |
| `investigacao_historico_veicular` | Histórico veicular (SP) por CPF ou CNPJ. |
| `investigacao_prf_infracoes` | Infrações da Polícia Rodoviária Federal por placa + RENAVAM. |
| `investigacao_situacao_eleitoral` | Situação eleitoral de uma pessoa (TSE). |
| `investigacao_titulo_eleitoral` | Título e local de votação (TSE). |
| `investigacao_beneficios_sociais` | Benefícios sociais recebidos por um CPF (Bolsa Família, BPC, etc.). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Pré-pago (carteira de créditos), paga por uso. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_investigacao`.


---

## Suporte

- 📧 [investigacao@mcp.ai](mailto:investigacao@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/investigacao-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_investigacao` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
