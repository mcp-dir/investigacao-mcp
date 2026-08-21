# Ferramentas

Investigação Cadastral expõe 20 ferramentas (todas somente leitura).

### 1. `investigacao_pessoa_fisica`
**Input**: `CPF` (opcional), `completo` (opcional)

Dados cadastrais completos de um CPF: nome, contato (telefone/email), endereço, renda estimada e faixa salarial.

### 2. `investigacao_pessoa_juridica`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Dados cadastrais completos de um CNPJ.

### 3. `investigacao_localizacao`
**Input**: `CPF` (opcional), `NAME` (opcional), `SURNAME` (opcional), `DOB` (opcional), `completo` (opcional)

Localização de uma pessoa (nome, endereço, telefone, email).

### 4. `investigacao_enriquecimento`
**Input**: `CELULAR` (opcional), `EMAIL` (opcional), `completo` (opcional)

Descobre a pessoa por trás de um celular e/ou email (enriquecimento reverso).

### 5. `investigacao_vinculos_societarios`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Vínculos/relacionamentos societários de uma pessoa ou empresa.

### 6. `investigacao_participacoes`
**Input**: `CNPJ` (opcional), `completo` (opcional)

QSA + participações societárias de um CNPJ (sócios e empresas ligadas).

### 7. `investigacao_beneficiario_final`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Beneficiário final (UBO) de uma empresa ou pessoa.

### 8. `investigacao_aml`
**Input**: `CPF` (opcional), `completo` (opcional)

Rede de vínculos societários para prevenção à lavagem de dinheiro, por CPF.

### 9. `investigacao_renda`
**Input**: `CPF` (opcional), `completo` (opcional)

Nível socioeconômico e renda estimada de um CPF.

### 10. `investigacao_vinculo_empregaticio`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Vínculos empregatícios.

### 11. `investigacao_obito`
**Input**: `CPF` (opcional), `completo` (opcional)

Verificação de óbito por CPF.

### 12. `investigacao_propriedade_veicular`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Veículos no nome de uma pessoa ou empresa (frota) por CPF/CNPJ.

### 13. `investigacao_pis`
**Input**: `CPF` (opcional), `completo` (opcional)

PIS vinculado a um CPF.

### 14. `investigacao_veiculo_placa`
**Input**: `PLACA` (opcional), `completo` (opcional)

Dados e débitos de um veículo pela placa (não exige RENAVAM).

### 15. `investigacao_cnh`
**Input**: `CPF` (opcional), `completo` (opcional)

Dados da CNH (Carteira Nacional de Habilitação) por CPF.

### 16. `investigacao_historico_veicular`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Histórico veicular (SP) por CPF ou CNPJ.

### 17. `investigacao_prf_infracoes`
**Input**: `PLACA`, `RENAVAM`, `TIPO`, `completo` (opcional)

Infrações da Polícia Rodoviária Federal por placa + RENAVAM.

### 18. `investigacao_situacao_eleitoral`
**Input**: `NOME` (opcional), `CPF` (opcional), `NUMEROTITULOELEITORAL` (opcional), `DATANASCIMENTO` (opcional), `completo` (opcional)

Situação eleitoral de uma pessoa (TSE).

### 19. `investigacao_titulo_eleitoral`
**Input**: `NOME` (opcional), `CPF` (opcional), `NUMEROTITULOELEITORAL` (opcional), `DATANASCIMENTO`, `NOMEMAE`, `completo` (opcional)

Título e local de votação (TSE).

### 20. `investigacao_beneficios_sociais`
**Input**: `CPF` (opcional), `completo` (opcional)

Benefícios sociais recebidos por um CPF (Bolsa Família, BPC, etc.).

## Prompts de exemplo

```
Localize a pessoa do CPF 000.000.000-00 (endereço e telefone)
Quais empresas o CNPJ X tem vínculo societário?
Quem é o beneficiário final dessa empresa?
```
