# bi-bodedono
Systema costumizado para criação e disponibilização de análises de BI do Grupo Bode do Nô


# Teste:

# Dicionário de Dados – Teknisa Retail / Ambiente Zmart

> Data de referência da última atualização deste documento: **26/11/2025**  
> Todas as datas de atualização por tabela referem-se à análise das amostras enviadas até o momento neste chat.

---

### Dataset / Tabela: TEKNISA.ACESSOFM

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM ACESSOFM WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.ADMINCARTFIL

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM ADMINCARTFIL WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.ALIQIMPFIS

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: `SELECT * FROM ALIQIMPFIS WHERE ROWNUM <= 100` (100 registros).

**Chaves (inferido da amostra)**  
- Candidata a PK lógica: **`CDFILIAL + CDPRODUTO`**.  
- Possíveis FKs: `CDFILIAL` → filiais; `CDPRODUTO` → produtos; códigos fiscais → tabelas de domínio fiscal.

| Coluna            | Tipo de dado                 | Descrição                                                                                                                             | Exemplos              |
|-------------------|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| CDFILIAL          | texto (código/identificador) | Código da filial/loja onde a regra/alíquota fiscal do produto é válida.                                                              | `0002`                |
| CDPRODUTO         | texto (código/identificador) | Código interno do produto ao qual a alíquota fiscal se aplica.                                                                       | `0000000045`          |
| VRPEALIMPFIS      | numérico (decimal)           | Percentual da alíquota de imposto fiscal configurada para o produto na filial.                                                       | `20,5`                |
| CDIMPOSTO         | texto (código/identificador) | Código do imposto principal associado à regra fiscal (ex.: ICMS/IPI).                                                                | `0`                   |
| IDTPIMPOSFIS      | texto (código/identificador) | Indicador do tipo de imposto fiscal (ex.: tributado, isento, substituição tributária).                                               | `T`                   |
| DTULTATUALIF      | data/hora                    | Data e hora da última atualização da alíquota/imposto fiscal para o registro.                                                        | `28/11/2024 14:54:13` |
| IDINCIDEPISCOF    | texto (código/identificador) | Indicador de incidência de PIS/COFINS (`S` = com incidência, `N` = sem incidência).                                                  | `S`                   |
| DTINCLUSAO        | data/hora                    | Data e hora em que o registro foi incluído na tabela.                                                                                | `28/11/2024 08:47:42` |
| DTULTATU          | data/hora                    | Data e hora da última alteração do registro na tabela.                                                                               | `28/11/2024 09:52:30` |
| NRORGINCLUSAO     | texto (código/identificador) | Número de origem/controle da inclusão do registro (processo, lote, integração).                                                      | `5292`                |
| CDOPERINCLUSAO    | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                                    | `1`                   |
| NRORGULTATU       | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                                         | `5292`                |
| CDOPERULTATU      | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                                          | `1`                   |
| IDATIVO           | texto (indicador)            | Indicador se o registro de alíquota está ativo (`S` = ativo, `N` = inativo).                                                         | `S`                   |
| VRALIQIBPT        | numérico (decimal)           | Percentual de alíquota IBPT (carga tributária aproximada). **Sem valores na amostra** (inferido pelo nome).                          | –                     |
| CDCSTICMS         | texto (código/identificador) | Código CST/CSOSN de ICMS configurado para o produto.                                                                                 | `20`                  |
| CDCSTPISCOF       | texto (código/identificador) | Código CST de PIS/COFINS utilizado na tributação do produto.                                                                         | `06`                  |
| CDCFOPPFIS        | texto (código/identificador) | Código CFOP padrão para operações fiscais do produto.                                                                                | `5102`                |
| CDREGRAIT         | texto (código/identificador) | Código da regra de tributação (impostos) aplicada ao produto. **Sem valores na amostra**.                                            | –                     |
| VRALIQIBPTES      | numérico (decimal)           | Percentual de alíquota IBPT para operações interestaduais/especiais. **Sem valores na amostra**.                                     | –                     |
| VRPERCREDUCAO     | numérico (decimal)           | Percentual de redução da base de cálculo ou da alíquota do imposto.                                                                  | `89,66`               |
| IDMODALBASECALC   | texto (código/identificador) | Modalidade de cálculo da base de ICMS (ex.: valor da operação, preço tabelado etc.).                                                | `3`                   |
| CDREGRAITPC       | texto (código/identificador) | Código de regra de tributação específica para PIS/COFINS. **Sem valores na amostra**.                                                | –                     |
| CDCEST            | texto (código/identificador) | Código CEST do produto, utilizado em operações com ICMS-ST.                                                                          | `17.084.00`           |
| VRALIQPIS         | numérico (decimal)           | Percentual de alíquota de PIS aplicado ao produto.                                                                                   | `0`                   |
| VRALIQCOFINS      | numérico (decimal)           | Percentual de alíquota de COFINS aplicado ao produto.                                                                                | `0`                   |
| NRORG             | texto (código/identificador) | Número de origem/identificador do processo de carga/integração das regras fiscais.                                                   | `5292`                |
| VRALIQFCP         | numérico (decimal)           | Percentual de alíquota do FCP (Fundo de Combate à Pobreza). **Sem valores na amostra**.                                              | –                     |
| VRPEALIMPFISEF    | numérico (decimal)           | Percentual de alíquota fiscal efetiva (após reduções/benefícios). **Sem valores na amostra**.                                        | –                     |
| VRPERCREDUCAOEF   | numérico (decimal)           | Percentual de redução efetiva da base/alíquota, considerando regras especiais. **Sem valores na amostra**.                           | –                     |
| CDCBENEF          | texto (código/identificador) | Código de benefício fiscal associado ao produto (isenção, redução, incentivo). **Sem valores na amostra**.                           | –                     |
| VRALIQICMSDES     | numérico (decimal)           | Percentual de alíquota de ICMS desonerado ou reduzido. **Sem valores na amostra**.                                                   | –                     |
| CDNATUREC         | texto (código/identificador) | Código de natureza da receita (para fins de ISS/SPED). **Sem valores na amostra**.                                                   | –                     |
| VRALIQISS         | numérico (decimal)           | Percentual de alíquota de ISS aplicado ao serviço/produto. **Sem valores na amostra**.                                               | –                     |
| CDITEMLISTASERV   | texto (código/identificador) | Código do item na lista de serviços da legislação de ISS. **Sem valores na amostra**.                                                | –                     |
| IDEXIGIBILISS     | texto (código/identificador) | Indicador de exigibilidade do ISS (exigível, imune, não incidência, suspensão etc.). **Sem valores na amostra**.                     | –                     |
| IDINCENTIVOISS    | texto (código/identificador) | Indicador de existência de incentivo fiscal de ISS. **Sem valores na amostra**.                                                      | –                     |
| CDSERVICOISS      | texto (código/identificador) | Código de serviço para fins de ISS na prefeitura/legislação municipal. **Sem valores na amostra**.                                   | –                     |
| CDCCREDPRES       | texto (código/identificador) | Código de crédito presumido aplicável ao produto/serviço. **Sem valores na amostra**.                                                | –                     |
| VRALIQCREDPRES    | numérico (decimal)           | Percentual de crédito presumido aplicado. **Sem valores na amostra**.                                                                | –                     |
| CDREGRAFISPDV     | texto (código/identificador) | Código da regra fiscal utilizada no PDV para o produto. **Sem valores na amostra**.                                                  | –                     |

---

### Dataset / Tabela: TEKNISA.ARQCAT52

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM ARQCAT52 WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.ARQMAGNETICO

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM ARQMAGNETICO WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.ARQUIVOS

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM ARQUIVOS WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.ARQXMLNFCESAT

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: `SELECT * FROM ARQXMLNFCESAT WHERE ROWNUM <= 100` (100 registros).

**Chaves (inferido da amostra)**  
- Candidata a PK lógica: **`CDFILIAL + CDCAIXA + NRSEQVENDA`**.  
- Possíveis FKs: `CDFILIAL` → filiais; `CDCAIXA` → caixas; combinação com `NRSEQVENDA` → movimento de venda.

| Coluna           | Tipo de dado                 | Descrição                                                                                                                   | Exemplos                  |
|------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------|---------------------------|
| CDFILIAL         | texto (código/identificador) | Código da filial/loja em que a venda da NFC-e/SAT foi realizada.                                                            | `0008`                    |
| CDCAIXA          | texto (código/identificador) | Código do caixa (PDV) que emitiu a NFC-e/SAT.                                                                               | `001`                     |
| NRSEQVENDA       | texto (código/identificador) | Número sequencial da venda no caixa, identificando unicamente a venda dentro da filial/caixa.                              | `0000005644`              |
| DSARQXMLNFCE     | texto (XML)                  | Conteúdo XML da NFC-e/SAT gerada na venda (NFe, protocolo, chave de acesso, etc.).                                          | `<?xml version="1.0"...`  |
| DSARQXMLCANCNFCE | texto (XML)                  | Conteúdo XML de cancelamento da NFC-e, quando há evento de cancelamento. **Sem valores na amostra**.                       | –                         |
| NRORG            | texto (código/identificador) | Número de origem/controle do processo de carga/integração dos XMLs.                                                         | `5292`                    |
| IDATIVO          | texto (indicador)            | Indicador de status do registro (`S` = ativo, `N` = inativo).                                                               | `S`                       |
| DTINCLUSAO       | data/hora                    | Data e hora de inclusão do registro/arquivo XML na tabela. **Sem valores na amostra** (inferido pelo nome).                | –                         |
| DTULTATU         | data/hora                    | Data e hora da última atualização do registro. **Sem valores na amostra**.                                                  | –                         |
| NRORGINCLUSAO    | texto (código/identificador) | Número de origem/controle da inclusão (ex.: lote de importação, processo).                                                  | `5292`                    |
| CDOPERINCLUSAO   | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                           | `1`                       |
| NRORGULTATU      | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                                | `5292`                    |
| CDOPERULTATU     | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                                 | `1`                       |

---

### Dataset / Tabela: TEKNISA.AUTGRUPOP

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: `SELECT * FROM AUTGRUPOP WHERE ROWNUM <= 100` (4 registros).

**Chaves (inferido da amostra)**  
- Candidata a PK: **`IDAUTGRUPOP`** (único na amostra).  
- Chave de negócio provável: **`CDGRUPOPER + IDAUTGRUPOP`**.  
- Possíveis FKs: `CDGRUPOPER` → grupos de operação; `CDSETOR` → setores; `CDFILIAL` → filiais.

| Coluna         | Tipo de dado                 | Descrição                                                                                                           | Exemplos        |
|----------------|------------------------------|---------------------------------------------------------------------------------------------------------------------|-----------------|
| CDGRUPOPER     | texto (código/identificador) | Código do grupo de operação/operador ao qual a autorização está vinculada.                                         | `01`            |
| IDAUTGRUPOP    | texto (código/identificador) | Identificador da autorização do grupo de operação (código lógico da permissão/regra).                               | `PRVC`          |
| NRAUTGRUPOP    | texto (código/identificador) | Número/ordem da autorização dentro do grupo de operação.                                                            | `001`           |
| CDSETOR        | texto (código/identificador) | Código do setor ao qual a autorização se aplica. **Sem valores na amostra**.                                       | –               |
| DTULTATUAGOP   | data/hora                    | Data e hora da última atualização da configuração da autorização do grupo de operação.                              | `09/05/2025 09:42:56` |
| CDFILIAL       | texto (código/identificador) | Código da filial/loja onde a autorização é válida (quando a regra é específica por filial). **Sem valores na amostra**. | –          |
| DTINCLUSAO     | data/hora                    | Data e hora em que o registro de autorização foi incluído na tabela.                                               | `09/05/2025 09:42:56` |
| DTULTATU       | data/hora                    | Data e hora da última atualização do registro na tabela.                                                           | `09/05/2025 09:42:56` |
| NRORGINCLUSAO  | texto (código/identificador) | Número de origem/controle da inclusão do registro. **Nulo ou parcial na amostra**.                                  | `5292` (ex.)    |
| CDOPERINCLUSAO | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                  | `#SUP_TEKNISA`  |
| NRORGULTATU    | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                       | `5292`          |
| CDOPERULTATU   | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                        | `#SUP_TEKNISA`  |
| IDATIVO        | texto (indicador)            | Indicador de status da autorização (`S` = ativo, `N` = inativo).                                                   | `S`             |
| NRORG          | texto (código/identificador) | Número de origem/controle geral do processo de configuração (lote/carga).                                          | `5292`          |

---

### Dataset / Tabela: TEKNISA.BAIRRO

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: `SELECT * FROM BAIRRO WHERE ROWNUM <= 100` (100 registros).

**Chaves (inferido da amostra)**  
- `CDBAIRRO` não é único globalmente.  
- Candidata a PK lógica: **`CDPAIS + SGESTADO + CDMUNICIPIO + CDBAIRRO`**.  
- Possíveis FKs: `CDPAIS` → países; `SGESTADO` → estados; `CDMUNICIPIO` → municípios.

| Coluna         | Tipo de dado                 | Descrição                                                                                                                | Exemplos            |
|----------------|------------------------------|--------------------------------------------------------------------------------------------------------------------------|---------------------|
| CDPAIS         | texto (código/identificador) | Código do país ao qual o bairro pertence (ex.: `0055` = Brasil).                                                        | `0055`              |
| SGESTADO       | texto (código/identificador) | Sigla do estado onde o bairro está localizado.                                                                          | `SP`, `MG`          |
| CDMUNICIPIO    | texto (código/identificador) | Código do município ao qual o bairro pertence (código interno/IBGE).                                                   | `9409`, `4123`      |
| CDBAIRRO       | texto (código/identificador) | Código interno do bairro (único em conjunto com país, estado e município).                                             | `0000020972`        |
| NMBAIRRO       | texto                        | Nome do bairro.                                                                                                          | `centro`            |
| CDREGIAOMUNI   | texto (código/identificador) | Código da região dentro do município (região administrativa, zona, etc.). **Sem valores na amostra**.                   | –                   |
| DTULTATUBAIR   | data/hora                    | Data e hora da última atualização específica do cadastro de bairro.                                                     | `22/11/2024 12:57:12` |
| VRTXENTREGA    | numérico (decimal)           | Valor adicional de taxa de entrega configurado para o bairro. Na amostra, `0` ou nulo (sem uso efetivo).                | `0`                 |
| QTHORAENTREGA  | numérico (inteiro)           | Quantidade de horas de prazo de entrega estimado para o bairro. Na amostra, `0` (sem parametrização efetiva).           | `0`                 |
| DTINCLUSAO     | data/hora                    | Data e hora em que o registro de bairro foi incluído na tabela.                                                         | `22/11/2024 12:57:12` |
| DTULTATU       | data/hora                    | Data e hora da última alteração do registro na tabela.                                                                  | `22/11/2024 12:57:12` |
| NRORGINCLUSAO  | texto (código/identificador) | Número de origem/controle da inclusão do registro (lote/processo de carga).                                            | `20`                |
| CDOPERINCLUSAO | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                       | `000000004734`      |
| NRORGULTATU    | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                            | `20`                |
| CDOPERULTATU   | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                             | `000000004734`      |
| IDATIVO        | texto (indicador)            | Indicador se o cadastro do bairro está ativo (`S` = ativo, `N` = inativo).                                              | `S`                 |
| NRORG          | texto (código/identificador) | Número de origem/controle geral da carga/cadastro.                                                                      | `5292`              |

---

### Dataset / Tabela: TEKNISA.BASECALC

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM BASECALC WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.BASECALCTPOPER

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM BASECALCTPOPER WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.BENEFICIOCAMP

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM BENEFICIOCAMP WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.BENEFICIOFOS

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM BENEFICIOFOS WHERE ROWNUM <= 100`): **sem registros retornados**.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.BRCAMPCOMPGANHE

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: `SELECT * FROM BRCAMPCOMPGANHE WHERE ROWNUM <= 100` (28 registros).

**Entendimento funcional**  
Tabela de **produtos participantes** de campanhas do tipo **“Compre e Ganhe”**.

**Chaves (inferido da amostra)**  
- Candidata a PK lógica: **`CDCAMPCOMPGANHE + CDPRODUTO`** (não se repete na amostra).  
- Possíveis FKs:
  - `CDCAMPCOMPGANHE` → tabela de cabeçalho da campanha “Compre e Ganhe”.
  - `CDPRODUTO` → tabela de produtos.

| Coluna           | Tipo de dado                 | Descrição                                                                                                                   | Exemplos              |
|------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-----------------------|
| CDCAMPCOMPGANHE  | texto (código/identificador) | Código da campanha do tipo “Compre e Ganhe” à qual o produto está vinculado.                                               | `6`, `5`, `1`         |
| DTINIVGCAMPCG    | data/hora                    | Data e hora de início da vigência da campanha “Compre e Ganhe” para o produto.                                             | `20/01/2025 00:00:00` |
| CDPRODUTO        | texto (código/identificador) | Código do produto participante da campanha.                                                                                | `0000000045`          |
| NRORG            | texto (código/identificador) | Número de origem/controle da carga/integração das campanhas (lote/processo).                                               | `5292`                |
| IDATIVO          | texto (indicador)            | Indicador se o vínculo campanha x produto está ativo (`S` = ativo, `N` = inativo).                                         | `S`                   |
| DTINCLUSAO       | data/hora                    | Data e hora da inclusão do vínculo campanha x produto. **Sem valores na amostra** (campo ainda não preenchido).            | –                     |
| DTULTATU         | data/hora                    | Data e hora da última alteração do vínculo campanha x produto. **Sem valores na amostra**.                                 | –                     |
| NRORGINCLUSAO    | texto (código/identificador) | Número de origem/controle da inclusão do registro (normalmente repete o mesmo NRORG em todas as linhas).                   | `5292`                |
| CDOPERINCLUSAO   | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                           | `1`                   |
| NRORGULTATU      | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                                | `5292`                |
| CDOPERULTATU     | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                                 | `1`                   |


---

### Dataset / Tabela: TEKNISA.BRINDECAMPANHA

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM BRINDECAMPANHA WHERE ROWNUM <= 100`): **sem registros retornados**.

> Observação: até a data acima, a aplicação não retornou nenhum registro para esta tabela na operação atual.  
> A estrutura de colunas ainda não pôde ser inferida por ausência de dados.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.CADBIOMETRIA

Última atualização dos dados desta tabela: **26/11/2025**  
Situação na consulta (`SELECT * FROM CADBIOMETRIA WHERE ROWNUM <= 100`): **sem registros retornados**.

> Observação: até a data acima, a aplicação não retornou nenhum registro para esta tabela na operação atual.  
> A estrutura de colunas ainda não pôde ser inferida por ausência de dados.

| Coluna         | Tipo de dado | Descrição                                                                                               | Exemplos |
|----------------|-------------|---------------------------------------------------------------------------------------------------------|----------|
| (desconhecido) | desconhecido | Estrutura de colunas ainda não mapeada. Tabela sem registros na operação da empresa na data indicada. | –        |

---

### Dataset / Tabela: TEKNISA.CAIXA

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: resultado de `SELECT * FROM CAIXA WHERE ROWNUM <= 100` (100 registros, 305 colunas).

**Observações de chaves (inferido da amostra):**

- Candidata a PK lógica: **CDFILIAL + CDCAIXA** (combinação única na amostra).
- Possíveis FKs:
  - `CDFILIAL` → tabela de filiais.
  - `CDLOJA` → tabela de lojas.
  - `CDSETOR` → tabela de setores.
- Relação esperada:
  - Tabela `ARQXMLNFCESAT` deve referenciar `CAIXA` pela combinação `CDFILIAL + CDCAIXA`.

| Coluna | Tipo de dado | Descrição | Exemplos |
|--------|--------------|-----------|----------|
| CDFILIAL | texto (código/identificador) | Código da filial/loja em que o caixa está cadastrado. | `0002` |
| CDCAIXA | texto (código/identificador) | Código do caixa (PDV) dentro da filial. | `002` |
| NMCAIXA | texto | Nome ou identificação amigável do caixa, exibido para o usuário. | `CAIXA02` |
| CDLOJA | texto (código/identificador) | Código da loja associada à configuração do caixa. | `001` |
| CDALMOXARIFE | texto (código/identificador) | Campo de código técnico associado ao caixa; significado funcional específico ainda não mapeado. | `–` |
| CDLOCALESTOQ | texto (código/identificador) | Campo de código técnico associado ao caixa; significado funcional específico ainda não mapeado. | `–` |
| DSDIRFOTOPR | texto | Campo descritivo/configuração textual do caixa; significado funcional ainda não mapeado. | `–` |
| IDCONFVENDA | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `1` |
| IDGERANOTA | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| IDPORTABAL | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `COM2` |
| IDPORTAIMP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| IDTIPOIMP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| IDTPTELAVE | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `5` |
| IDVEPORTABAL | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `9600` |
| TPEXTFOTOPR | texto (desconhecido) | Campo técnico relacionado ao caixa; significado funcional ainda não mapeado. | `–` |
| VRABERCAIX | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `0` |
| VRDIFCAIX | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| IDENTRSAIDOP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| CDTIPOOPER | texto (código/identificador) | Campo de código técnico associado ao caixa; significado funcional específico ainda não mapeado. | `–` |
| IDCAMPOPESQ | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `V` |
| IDPERANTVEND | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `S` |
| IDULTVENDA | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `S` |
| VRCREDCAIXA | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRCREDUTILI | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRSALDCAIXA | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRLIMCAIXA | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRLIMDIAVEND | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRTROCA | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| VRSALDVEND | numérico (decimal) | Valor monetário ou numérico configurado para o caixa. | `–` |
| CDSERVREST | texto (código/identificador) | Campo de código técnico associado ao caixa; significado funcional específico ainda não mapeado. | `–` |
| CDUSUAREST | texto (código/identificador) | Campo de código técnico associado ao caixa; significado funcional específico ainda não mapeado. | `–` |
| NRSENHAREST | texto (código/identificador) | Número ou sequência de controle/configuração relacionada ao caixa. | `–` |
| IDUSAREST | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| IDIMPRES | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `–` |
| IDIMPCONTAPRE | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDCOZIN | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDFATUR | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDFRENTE | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDFLUXO | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDFICH | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPIMPDIRETA | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPEDFICHREL | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPPOSPICAUT | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPTALCAUT | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSALDCAIXAPOS | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDIMPCANCAVIS | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDCONFIRVEND | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDCONFIRPF | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDCONFIRPGTO | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDEMISPRINT | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDLCFRONTOFF | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `S` |
| IDCONFIRORDEM | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDUTILPRODGRD | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDEXIPESQAUT | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDALTEROP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `S` |
| IDCONFIRCOMP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAVEND | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAVENDCANC | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACANCITEM | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAALTITE | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAALTVALOR | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHADESCPER | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHADESCPRO | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACONCED | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACANCLI | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACANDEV | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAALTERFPG | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAREIMP | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACONFPG | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACXDIA | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHAFECHCAIX | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSENHACLOSPDV | texto (indicador) | Indicador/flag de configuração ou comportamento do caixa (`S`/`N`, `0`/`1` ou similar). | `N` |
| IDSOLNUMDEPFC     | texto (indicador)              | Indicador/flag de configuração do caixa; significado funcional específico ainda não mapeado.              | –        |
| IDSOLICITACPF     | texto (indicador)              | Indicador/flag de configuração do caixa; significado funcional específico ainda não mapeado.              | –        |
| IDGRAVAMFD        | texto (indicador)              | Indicador/flag de configuração do caixa; significado funcional específico ainda não mapeado.              | –        |
| IDBAIXAPERIF      | texto (indicador)              | Indicador/flag de configuração do caixa; significado funcional específico ainda não mapeado.              | –        |
| IDINFREDZNCAD     | texto (indicador)              | Indicador/flag de configuração do caixa; significado funcional específico ainda não mapeado.              | –        |
| IDTIPOMICROTERM   | texto (indicador)              | Indicador/flag de configuração do tipo de micro/terminal do caixa; significado detalhado ainda pendente.  | –        |
| CDSETOR           | texto (código/identificador)   | Código de setor associado ao caixa para fins de controle/relatórios; significado exato ainda não mapeado. | –        |
| IDPAISINTEGRA     | texto (indicador)              | Indicador de integração por país ou contexto similar; significado exato ainda não mapeado.                | –        |
| CDPREFINTGCOL     | texto (código/identificador)   | Código de preferência/configuração de integração; significado funcional ainda não mapeado.                | –        |
| NRCUPINIINTGCOL   | numérico (inteiro/sequencial)  | Número/sequência relacionado a cupom em integração/coleta; significado exato ainda não mapeado.           | –        |
| NRCUPFININTGCOL   | numérico (inteiro/sequencial)  | Número/sequência relacionado a cupom em integração/coleta; significado exato ainda não mapeado.           | –        |
| DSRESOLINTGCOL    | texto                          | Texto/descrição de resolução/configuração de integração; significado detalhado ainda não mapeado.         | –        |
| IDPERCOMVENCPDC   | texto (indicador)              | Indicador de período/controle de vencimento; significado exato ainda não mapeado.                         | –        |
| DSMENSCPFCUP      | texto                          | Mensagem exibida relacionada a CPF em cupom; texto configurável no caixa.                                 | –        |
| IDLCDBARBALATOL   | texto (indicador)              | Indicador de leitura/cadastro de código de barras; significado exato ainda não mapeado.                   | –        |
| NRPOSINICODBARR   | numérico (inteiro/sequencial)  | Posição inicial de leitura/gravação de código de barras; significado detalhado ainda não mapeado.         | –        |
| NRPOSFINCODBARR   | numérico (inteiro/sequencial)  | Posição final de leitura/gravação de código de barras; significado detalhado ainda não mapeado.           | –        |
| NRPOSINIQTCDBAR   | numérico (inteiro/sequencial)  | Posição inicial para quantidade no código de barras; significado exato ainda não mapeado.                 | –        |
| NRPOSFINQTCDBAR   | numérico (inteiro/sequencial)  | Posição final para quantidade no código de barras; significado exato ainda não mapeado.                   | –        |
| NRPOSINIVRCDBAR   | numérico (inteiro/sequencial)  | Posição inicial para valor no código de barras; significado exato ainda não mapeado.                      | –        |
| NRPOSFINVRCDBAR   | numérico (inteiro/sequencial)  | Posição final para valor no código de barras; significado exato ainda não mapeado.                        | –        |
| IDIMPCOMPDEBCON   | texto (indicador)              | Indicador para impressão de comprovante de débito/conta; significado exato ainda não mapeado.             | –        |
| IDIMPCOMPCREDPE   | texto (indicador)              | Indicador para impressão de comprovante de crédito; significado exato ainda não mapeado.                  | –        |
| IDIMPCOMPCUPVEN   | texto (indicador)              | Indicador para impressão de cupom de venda; significado exato ainda não mapeado.                          | –        |
| IDGERAARQVNDRIO   | texto (indicador)              | Indicador para geração de arquivo/registro de vendas; significado exato ainda não mapeado.                | –        |
| IDTPCONTRREPIQ    | texto (indicador)              | Indicador de tipo de controle de repetição/repique; significado exato ainda não mapeado.                  | –        |
| IDPERABERCOMCXA   | texto (indicador)              | Indicador/período de abertura automática/condicionada do caixa; significado exato ainda não mapeado.      | –        |
| NRDIASVENDAMSDE   | numérico (inteiro/sequencial)  | Número de dias relacionados a manutenção/apagamento de vendas; significado detalhado ainda não mapeado.   | –        |
| IDFREQLIMPVENDA   | texto (indicador)              | Indicador de frequência de limpeza de vendas; significado exato ainda não mapeado.                        | –        |
| NRDIASBXVNDMSDE   | numérico (inteiro/sequencial)  | Número de dias para baixa/exclusão de vendas; significado exato ainda não mapeado.                        | –        |
| IDUTILBINADEL     | texto (indicador)              | Indicador de uso de algum recurso “bina”/discador; significado exato ainda não mapeado.                   | –        |
| IDEXIBTNIMPCTFS   | texto (indicador)              | Indicador de exibição de botão de impressão de cupom fiscal; significado exato ainda não mapeado.         | –        |
| IDEXIBTNLISPRFS   | texto (indicador)              | Indicador de exibição de botão de lista/relatório fiscal; significado exato ainda não mapeado.            | –        |
| CDLAYOUTIMP       | texto (código/identificador)   | Código de layout de impressão utilizado pelo caixa.                                                       | –        |
| IDSOLDIGCONS      | texto (indicador)              | Indicador se é solicitada digitação/confirmação em determinada operação; significado exato pendente.      | –        |
| IDPALFUTRABRCXA   | texto (indicador)              | Indicador de parametrização de operação futura de caixa; significado exato ainda não mapeado.             | –        |
| DTINCLUSAO        | data/hora                      | Data/hora de inclusão do registro de configuração do caixa.                                               | –        |
| DTULTATU          | data/hora                      | Data/hora da última atualização do registro de configuração do caixa.                                     | –        |
| NRORGINCLUSAO     | numérico (inteiro/sequencial)  | Número/identificador de origem da inclusão (lote/processo).                                               | –        |
| CDOPERINCLUSAO    | texto (código/identificador)   | Código do operador/usuário responsável pela inclusão do registro.                                         | –        |
| NRORGULTATU       | numérico (inteiro/sequencial)  | Número/identificador de origem da última atualização do registro.                                         | –        |
| CDOPERULTATU      | texto (código/identificador)   | Código do operador/usuário responsável pela última atualização do registro.                               | –        |
| IDSOLCONICNFIS    | texto (indicador)              | Indicador se solicita confirmação em operação não-fiscal; significado exato ainda não mapeado.            | –        |
| IDSOLDIGOBSDC     | texto (indicador)              | Indicador se solicita digitação de observação/desconto; significado exato ainda não mapeado.              | –        |
| IDGERALOGFOS      | texto (indicador)              | Indicador de geração de log relacionado a FOS ou módulo similar; significado exato ainda não mapeado.     | –        |
| VRPEMAXREPIQVND   | numérico (decimal)             | Valor percentual máximo de repetição/lote de vendas; significado exato ainda não mapeado.                 | –        |
| IDSOLTPSANGRIACX  | texto (indicador)              | Indicador se solicita tipo de sangria de caixa; significado exato ainda não mapeado.                      | –        |
| IDIMPCOMPVCP      | texto (indicador)              | Indicador de impressão de comprovante VCP; significado exato ainda não mapeado.                           | –        |
| IDCONSCAIXATC     | texto (indicador)              | Indicador de consulta específica de caixa/terminal; significado exato ainda não mapeado.                  | –        |
| IDUTILFECHCEGO    | texto (indicador)              | Indicador de utilização de fechamento “cego” (sem saldo); significado exato ainda não mapeado.            | –        |
| DSGRANCONTRIB     | texto                          | Descrição/mensagem relacionada a contribuinte/grande contribuinte; significado exato ainda não mapeado.   | –        |
| DSAUTORETENT      | texto                          | Descrição/mensagem de autorização/retentiva; significado exato ainda não mapeado.                         | –        |
| DSMSGAUTOPAG      | texto                          | Mensagem exibida em casos de autorização de pagamento; significado exato ainda não mapeado.               | –        |
| DSMSGLIBPAG       | texto                          | Mensagem exibida em casos de liberação de pagamento; significado exato ainda não mapeado.                 | –        |
| DSMSGPENPAG       | texto                          | Mensagem exibida em casos de pagamento pendente; significado exato ainda não mapeado.                     | –        |
| IDPERCONSEXT      | texto (indicador)              | Indicador de permissão de acesso/consulta externa; significado exato ainda não mapeado.                   | –        |
| IDPERIMPREXT      | texto (indicador)              | Indicador de permissão de impressão externa; significado exato ainda não mapeado.                         | –        |
| IDEXIEXTDIAS      | texto (indicador)              | Indicador relacionado à exibição externa com dias parametrizados; significado exato ainda não mapeado.    | –        |
| IDIMPEXTDIAS      | texto (indicador)              | Indicador relacionado à impressão externa com dias parametrizados; significado exato ainda não mapeado.   | –        |
| NRSEQIMPRLOJA1    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 1); significado exato ainda não mapeado.                     | –        |
| NRSEQIMPRLOJA2    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 2); significado exato ainda não mapeado.                     | –        |
| IDSINCCAIXADLV    | texto (indicador)              | Indicador de sincronização de caixa com delivery; significado exato ainda não mapeado.                    | –        |
| IDGERBKPMSDE      | texto (indicador)              | Indicador para geração de backup MSDE/engine; significado exato ainda não mapeado.                        | –        |
| IDATIVO           | texto (indicador)              | Indicador se o registro de configuração do caixa está ativo (`S`/`N`).                                    | –        |
| IDTPEMISSAOFOS    | texto (indicador)              | Indicador/tipo de emissão FOS; significado exato ainda não mapeado.                                       | –        |
| NRSEQIMPRLOJA3    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 3); significado exato ainda não mapeado.                     | –        |
| IDTIPOIMPNF3      | texto (indicador)              | Indicador/tipo de impressora NF3 ou canal 3; significado exato ainda não mapeado.                         | –        |
| CDPORTAIMPNF3     | texto (código/identificador)   | Código/configuração de porta de impressora NF3/canal 3.                                                   | –        |
| IDTPVENDIMPNF3    | texto (indicador)              | Indicador de tipo de venda para impressão NF3/canal 3; significado exato ainda não mapeado.              | –        |
| CDIMPRESSORA3     | texto (código/identificador)   | Código de impressora configurada para o canal 3.                                                          | –        |
| IDPRIMVEZEXPON    | texto (indicador)              | Indicador de “primeira vez” exposição/execução; significado exato ainda não mapeado.                      | –        |
| CDSAT             | texto (código/identificador)   | Código de equipamento ou configuração SAT associada ao caixa.                                             | –        |
| IDSENHACUP        | texto (indicador)              | Indicador relacionado à senha/controle de cupom; significado exato ainda não mapeado.                     | –        |
| IDTPEQUSAT        | texto (indicador)              | Indicador/tipo de equipamento SAT; significado exato ainda não mapeado.                                   | –        |
| IDIMPPEDPROD      | texto (indicador)              | Indicador de impressão de pedidos de produção; significado exato ainda não mapeado.                       | –        |
| IDTPTEF           | texto (indicador)              | Indicador/tipo de TEF configurado para o caixa.                                                           | –        |
| CDPORTATEF        | texto (código/identificador)   | Código/porta utilizada para comunicação TEF.                                                              | –        |
| CDESTTEF          | texto (código/identificador)   | Código/identificador de estabelecimento TEF.                                                              | –        |
| NRSEQIMPRLOJA4    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 4); significado exato ainda não mapeado.                     | –        |
| IDOBRIGFECHCAIX   | texto (indicador)              | Indicador de obrigatoriedade de fechamento de caixa; significado exato ainda não mapeado.                | –        |
| CDSERIECX         | texto (código/identificador)   | Código de série associado ao caixa (fiscal ou interno).                                                   | –        |
| NRSEQIMPRLOJA5    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 5); significado exato ainda não mapeado.                     | –        |
| IDUTILSATCOMP     | texto (indicador)              | Indicador de utilização de SAT em determinado modo/composto; significado exato ainda não mapeado.         | –        |
| CDURLWSSAT        | texto (código/identificador)   | URL/endereço de web service SAT configurado para o caixa.                                                 | –        |
| DSSATHOST         | texto                          | Descrição/host do equipamento/servidor SAT.                                                               | –        |
| CDATIVASAT        | texto (código/identificador)   | Código/identificador de ativação SAT.                                                                     | –        |
| DSPRINTHOST       | texto                          | Descrição/host da impressora associada ao caixa.                                                          | –        |
| IDIMPAUTENTREG    | texto (indicador)              | Indicador de impressão automática de comprovante de entrega; significado exato ainda não mapeado.         | –        |
| IDAGRUPACMDAPC    | texto (indicador)              | Indicador de agrupamento de comandos/ações; significado exato ainda não mapeado.                          | –        |
| IDRECAUTDLV       | texto (indicador)              | Indicador de recebimento/autorização automática para delivery; significado exato ainda não mapeado.      | –        |
| IDVISTELPED       | texto (indicador)              | Indicador de visualização de tela de pedido; significado exato ainda não mapeado.                         | –        |
| IDFINPEDAUTDLV    | texto (indicador)              | Indicador de finalização automática de pedido de delivery; significado exato ainda não mapeado.           | –        |
| IDLEITURAQRCODE   | texto (indicador)              | Indicador de uso/leitura de QRCode no caixa.                                                              | –        |
| CDSERIEECP        | texto (código/identificador)   | Código de série ECF/ECP ou similar; significado exato ainda não mapeado.                                  | –        |
| IDPARCREDCAP      | texto (indicador)              | Indicador de parcelamento/crédito em capital; significado exato ainda não mapeado.                        | –        |
| IDUTILFOSCAT      | texto (indicador)              | Indicador de uso de FOS/CAT; significado exato ainda não mapeado.                                         | –        |
| IDLOCIMPENT       | texto (indicador)              | Indicador/local de impressão de entrega; significado exato ainda não mapeado.                             | –        |
| IDMOMENTOCPFVEN   | texto (indicador)              | Indicador do momento em que o CPF é solicitado na venda; significado exato ainda não mapeado.             | –        |
| IDINFNOMEEND      | texto (indicador)              | Indicador de impressão/uso de nome e endereço no cupom/documento.                                         | –        |
| CDVINCSATCX       | texto (código/identificador)   | Código de vínculo entre SAT e caixa.                                                                      | –        |
| NRSEQIMPRLOJA7    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 7); significado exato ainda não mapeado.                     | –        |
| DTULTIMALIMPEZA   | data/hora                      | Data/hora da última “limpeza”/rotina de manutenção ligada ao caixa.                                       | –        |
| IDIMPAUTCUPEXP    | texto (indicador)              | Indicador de impressão automática de cupom de exposição/expediente; significado exato ainda não mapeado.  | –        |
| CDCODATIVASAT     | texto (código/identificador)   | Código de ativação SAT complementar; significado exato ainda não mapeado.                                 | –        |
| NRORG             | numérico (inteiro/sequencial)  | Número de origem/lote de carga das configurações.                                                         | –        |
| IDABERCAIXDIGI    | texto (indicador)              | Indicador de abertura de caixa com digitação manual; significado exato ainda não mapeado.                 | –        |
| NRSEQIMPRLOJA6    | numérico (inteiro/sequencial)  | Sequência de impressão para loja (canal/slot 6); significado exato ainda não mapeado.                     | –        |
| IDIMPRIMENOTA     | texto (indicador)              | Indicador de impressão de nota/documento específico; significado exato ainda não mapeado.                 | –        |
| IDENVIAEMAIL      | texto (indicador)              | Indicador de envio de e-mail a partir do caixa.                                                           | –        |
| IDUTILABERAUTO    | texto (indicador)              | Indicador de uso de abertura automática de caixa.                                                         | –        |
| HRFECHCAIXAUTO    | texto                          | Horário configurado para fechamento automático de caixa.                                                  | –        |
| CDOPERABERAUTO    | texto (código/identificador)   | Código de operador utilizado em rotinas de abertura automática de caixa.                                  | –        |
| DSTXTRODAPEPARC   | texto                          | Texto de rodapé em documentos/parcelas emitidos pelo caixa.                                               | –        |
| IDVERGAVETANFIS   | texto (indicador)              | Indicador de verificação/tratativa de gaveta fiscal; significado exato ainda não mapeado.                 | –        |
| IDPERACESSOTER    | texto (indicador)              | Indicador de permissão de acesso a terceiro/terminal; significado exato ainda não mapeado.                | –        |
| NRMINSENHAAL      | numérico (inteiro/sequencial)  | Número de minutos para algo ligado à senha/alerta; significado exato ainda não mapeado.                   | –        |
| IDIMPPEDDLV       | texto (indicador)              | Indicador de impressão de pedidos de delivery; significado exato ainda não mapeado.                       | –        |
| NRCNPJLOJA        | numérico (inteiro/sequencial)  | CNPJ da loja relacionado ao caixa (sem formatação).                                                       | –        |
| CDEXTCAIXA        | texto (código/identificador)   | Código externo do caixa (integrações).                                                                    | –        |
| IDCAIXAEXCLUSIVO  | texto (indicador)              | Indicador de caixa exclusivo para alguma operação; significado exato ainda não mapeado.                   | –        |
| IDUTCXDRIVETHU    | texto (indicador)              | Indicador de uso de caixa em drive-thru; significado exato ainda não mapeado.                             | –        |
| IDFECHDIAPOS      | texto (indicador)              | Indicador de fechamento de dia pós-datado ou similar; significado exato ainda não mapeado.                | –        |
| IDINTDLVVOXLINE   | texto (indicador)              | Indicador de integração de delivery com Voxline; significado exato ainda não mapeado.                     | –        |
| DSDIRDLVVOXLINE   | texto                          | Diretório/caminho de integração Voxline para delivery.                                                    | –        |
| NRTIMERIMPCUP     | numérico (inteiro/sequencial)  | Tempo (timer) para impressão de cupom; significado exato ainda não mapeado.                               | –        |
| NRTIMERHRAGEN     | numérico (inteiro/sequencial)  | Tempo (timer) para agenda/horário; significado exato ainda não mapeado.                                   | –        |
| IDIMPOPCNF        | texto (indicador)              | Indicador de exibição de popup de confirmação; significado exato ainda não mapeado.                       | –        |
| IDRECAUTCREDPES   | texto (indicador)              | Indicador de recebimento/autorização em crédito pessoal; significado exato ainda não mapeado.             | –        |
| CDVERSAOOGO       | texto (código/identificador)   | Código/versão de algum componente OGO/integração; significado exato ainda não mapeado.                    | –        |
| DTULTCONEXAOOGO   | data/hora                      | Data/hora da última conexão com componente/serviço OGO.                                                   | –        |
| IDCXATIVOOGO      | texto (indicador)              | Indicador se o caixa está ativo para OGO/integração específica.                                          | –        |
| IDINFCONSTAA      | texto (indicador)              | Indicador de informação/integração com TAA; significado exato ainda não mapeado.                          | –        |
| IDRELFECCXTOT     | texto (indicador)              | Indicador de emissão de relatório de fechamento de caixa total; significado exato ainda não mapeado.      | –        |
| IDCOBTXSERVTAA    | texto (indicador)              | Indicador de cobrança de taxa de serviço TAA; significado exato ainda não mapeado.                        | –        |
| IDRECAUTVENCAT    | texto (indicador)              | Indicador de recebimento/autorização de vencidos em categoria; significado exato ainda não mapeado.       | –        |
| CDURLQRCODE       | texto (código/identificador)   | URL/base utilizada para geração de QRCode.                                                                | –        |
| CDIMPPEDPOS       | texto (código/identificador)   | Código de impressora ou layout de impressão de pedido POS.                                                | –        |
| IDGERAQRCODECAT   | texto (indicador)              | Indicador de geração de QRCode para categoria/operação; significado exato ainda não mapeado.              | –        |
| NRRANGEINI        | numérico (inteiro/sequencial)  | Número inicial de faixa/range usado em alguma parametrização.                                             | –        |
| NRRANGEFIN        | numérico (inteiro/sequencial)  | Número final de faixa/range usado em alguma parametrização.                                               | –        |
| IDOBRIGENTREDLV   | texto (indicador)              | Indicador de obrigatoriedade de dados de entrega em delivery.                                             | –        |
| IDQRCODEPINPAD    | texto (indicador)              | Indicador de uso de QRCode no pinpad; significado exato ainda não mapeado.                                | –        |
| NRSEQIMPRLOJA1BK  | numérico (inteiro/sequencial)  | Sequência de impressão “backup” para loja (canal 1).                                                      | –        |
| NRSEQIMPRLOJA2BK  | numérico (inteiro/sequencial)  | Sequência de impressão “backup” para loja (canal 2).                                                      | –        |
| NRSEQIMPRLOJA5BK  | numérico (inteiro/sequencial)  | Sequência de impressão “backup” para loja (canal 5).                                                      | –        |
| IDIMPRESOP        | texto (indicador)              | Indicador de impressão em operação específica (SOP/SOP?); significado exato ainda não mapeado.            | –        |
| IDIMPCANSATNFCE   | texto (indicador)              | Indicador de impressão de cancelamento SAT/NFC-e.                                                         | –        |
| IDIMPAUTENTREGPDV | texto (indicador)              | Indicador de impressão automática de entrega no PDV.                                                      | –        |
| IDABRGAVETNAABERT | texto (indicador)              | Indicador de abertura de gaveta na abertura de caixa; significado exato ainda não mapeado.                | –        |
| IDHABBARCODE      | texto (indicador)              | Indicador de habilitação de leitura de código de barras.                                                  | –        |
| IDUTILFONTEXP     | texto (indicador)              | Indicador de utilização de fonte expandida em impressões.                                                 | –        |
| IDVERLAYSAT       | texto (indicador)              | Indicador de verificação de layout SAT; significado exato ainda não mapeado.                              | –        |
| IDCONSPEDGRIDDLV  | texto (indicador)              | Indicador de consulta de pedidos em grid de delivery.                                                     | –        |
| IDENVCUPOMEMAIL   | texto (indicador)              | Indicador de envio de cupom por e-mail.                                                                   | –        |
| NRMAXSENHAPED     | numérico (inteiro/sequencial)  | Número máximo de senhas/pedidos; significado exato ainda não mapeado.                                     | –        |
| DSNFCESCHOST      | texto                          | Descrição/host para NFC-e (schema/serviço).                                                               | –        |
| NRDIASCONSMSDE    | numérico (inteiro/sequencial)  | Número de dias para considerar vendas/mensagens; significado exato ainda não mapeado.                     | –        |
| IDUTLFAUTABEFCH   | texto (indicador)              | Indicador de uso de fechamento automático de abertura/fechamento; significado exato ainda não mapeado.    | –        |
| NMCAIXAWIBX       | texto                          | Nome/identificação do caixa na integração Wibx ou similar.                                                | –        |
| IDIMPAUTCUPFOS    | texto (indicador)              | Indicador de impressão automática de cupom ligado ao FOS.                                                 | –        |
| IDPOPUPDLV        | texto (indicador)              | Indicador de exibição de popup para delivery.                                                             | –        |
| NRINICIONFCE      | numérico (inteiro/sequencial)  | Número inicial de sequência de NFC-e.                                                                     | –        |
| IDIMPCANPEDINT    | texto (indicador)              | Indicador de impressão de cancelamento de pedido interno.                                                 | –        |
| IDIMPPEDPRCIGE    | texto (indicador)              | Indicador de impressão de pedido de preço/IGE; significado exato ainda não mapeado.                       | –        |
| IDENVEMAILIMPCUP  | texto (indicador)              | Indicador de envio de e-mail juntamente com impressão de cupom.                                           | –        |
| IDUTLCOMUDIRMFE   | texto (indicador)              | Indicador de uso de diretório comum MFE; significado exato ainda não mapeado.                             | –        |
| IDUTILIMPFRONT    | texto (indicador)              | Indicador de uso de impressão “front” (frente de loja).                                                   | –        |
| IDIMPSENHACUP     | texto (indicador)              | Indicador de impressão da senha no cupom.                                                                 | –        |
| IDSOMADESCMANUA   | texto (indicador)              | Indicador de soma de descontos manuais; significado exato ainda não mapeado.                              | –        |
| IDHRMAXFECHCAIX   | texto (indicador)              | Indicador/param de horário máximo de fechamento de caixa.                                                 | –        |
| IDABERAGNDTAREF   | texto (indicador)              | Indicador de abertura/agenda de tarefa; significado exato ainda não mapeado.                              | –        |
| HRABERCAIXAUTO    | texto                          | Horário configurado para abertura automática de caixa.                                                    | –        |
| HRFECHACAIXA      | texto                          | Horário (não automático) de fechamento de caixa.                                                          | –        |
| DSENDIPSITEF2     | texto                          | Endereço IP/site para TEF2 ou canal TEF adicional.                                                        | –        |
| IDCANCVENDTCX     | texto (indicador)              | Indicador de cancelamento de vendas em determinado contexto de caixa.                                     | –        |
| CDPRODCMDAUTO     | texto (código/identificador)   | Código de produto comandado automaticamente; significado exato ainda não mapeado.                         | –        |
| NRCNPJTEFHOUSE    | numérico (inteiro/sequencial)  | CNPJ utilizado em configuração de TEF house; sem formatação.                                              | –        |
| IDSOLIMPCUPFIS    | texto (indicador)              | Indicador se solicita impressão de cupom fiscal.                                                          | –        |
| IDBTNIMPCUPFIS    | texto (indicador)              | Indicador de exibição/habilitação de botão de impressão de cupom fiscal.                                  | –        |
| CDTOKENTLS        | texto (código/identificador)   | Código/token TLS para comunicação segura; significado exato ainda não mapeado.                            | –        |
| CDTPCOMUNTLS      | texto (código/identificador)   | Código de tipo de comunicação TLS; significado exato ainda não mapeado.                                   | –        |
| CDTPPROXYTLS      | texto (código/identificador)   | Código de tipo de proxy para TLS; significado exato ainda não mapeado.                                    | –        |
| CDENPROXYTLS      | texto (código/identificador)   | Código/endereço de proxy TLS; significado exato ainda não mapeado.                                        | –        |
| IDEMITNFCECONTI   | texto (indicador)              | Indicador de emissão contínua/contingência de NFC-e; significado exato ainda não mapeado.                 | –        |
| IDIMPQRTOPDATA    | texto (indicador)              | Indicador de impressão de QRCode/topo com data; significado exato ainda não mapeado.                      | –        |
| IDNIMPRELFCEGO    | texto (indicador)              | Indicador de não impressão de relatório FCE ou similar; significado exato ainda não mapeado.              | –        |
| IDIMPPESAGEM      | texto (indicador)              | Indicador de impressão de dados de pesagem; significado exato ainda não mapeado.                          | –        |
| NRSERIALPOS       | numérico (inteiro/sequencial)  | Número de série do POS associado ao caixa.                                                                | –        |
| IDBLOQFECHACX     | texto (indicador)              | Indicador de bloqueio de fechamento de caixa; significado exato ainda não mapeado.                        | –        |
| IDUTILIZASEGMONITOR | texto (indicador)            | Indicador de utilização de segmento/monitoramento; significado exato ainda não mapeado.                   | –        |
| DSVIDEOPROMO      | texto                          | Descrição/caminho de vídeo promocional exibido no caixa.                                                 | –        |
| NMVIDEOPROMO      | texto                          | Nome do arquivo de vídeo promocional utilizado no caixa.                                                 | –        |

---

### Dataset / Tabela: TEKNISA.CAIXACUSTOMTAA

Última atualização dos dados desta tabela: **26/11/2025**  
Amostra analisada: resultado de `SELECT * FROM CAIXACUSTOMTAA WHERE ROWNUM <= 100` (5 registros, 12 colunas).

**Visão geral / chaves (inferido da amostra)**

- Função: vincular uma **configuração TAA** a um **caixa específico** (por filial/loja/caixa).
- Candidata a PK lógica: **`CDCONFIGTAA + CDFILIAL + CDLOJA + CDCAIXA`**.
- Possíveis FKs:
  - `CDCONFIGTAA` → tabela de configuração de TAA (não mapeada ainda).
  - `CDFILIAL + CDLOJA + CDCAIXA` → `TEKNISA.CAIXA`.

| Coluna          | Tipo de dado                 | Descrição                                                                                                           | Exemplos              |
|-----------------|------------------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------|
| CDCONFIGTAA     | texto (código/identificador) | Código da configuração TAA (perfil/regra de integração TAA) aplicada ao caixa.                                      | `00001`               |
| CDFILIAL        | texto (código/identificador) | Código da filial em que o caixa está localizado.                                                                    | `0008`                |
| CDLOJA          | texto (código/identificador) | Código da loja associada à filial/caixa.                                                                            | `001`                 |
| CDCAIXA         | texto (código/identificador) | Código do caixa (PDV) que recebe a configuração TAA.                                                                | `004`                 |
| NRORG           | texto (código/identificador) | Número de origem/controle do processo de carga/integração dessa configuração (lote, rotina, processo).             | `5292`                |
| IDATIVO         | texto (indicador)            | Indicador se o vínculo configuração TAA x caixa está ativo (`S` = ativo, `N` = inativo).                            | `S`                   |
| DTINCLUSAO      | data/hora                    | Data e hora em que o vínculo configuração TAA x caixa foi incluído na tabela.                                      | `04/02/2025 17:50:16` |
| DTULTATU        | data/hora                    | Data e hora da última atualização do vínculo configuração TAA x caixa.                                             | `04/02/2025 17:50:16` |
| NRORGINCLUSAO   | texto (código/identificador) | Número de origem/controle da inclusão do registro (geralmente o mesmo NRORG da carga/procedimento).                | `5292`                |
| CDOPERINCLUSAO  | texto (código/identificador) | Código do operador/usuário responsável pela inclusão do registro.                                                  | `1`                   |
| NRORGULTATU     | texto (código/identificador) | Número de origem/controle da última atualização do registro.                                                        | `5292`                |
| CDOPERULTATU    | texto (código/identificador) | Código do operador/usuário responsável pela última atualização do registro.                                        | `1`                   |
