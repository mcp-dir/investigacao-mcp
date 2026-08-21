# Investigação Cadastral

### Investigação Cadastral for Claude, ChatGPT and AI agents

Cadastral investigation of people and companies: location, corporate ties/relationships, participations, ultimate beneficial owner, estimated income, death and vehicle ownership. Platform-hosted, prepaid per query.

- 📊 **20 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Investigação Cadastral`, URL `https://api.mcp.ai/p_investigacao`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=investigacao&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9pbnZlc3RpZ2FjYW8ifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=investigacao&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_investigacao%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_investigacao
```

---

## 20 tools

| Tool | Description |
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

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_investigacao` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
