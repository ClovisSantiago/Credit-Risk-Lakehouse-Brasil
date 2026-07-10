[README.md](https://github.com/user-attachments/files/29907538/README.md)
# Credit-Risk-Lakehouse-Brasil
Projeto de Engenharia e Análise de Dados baseado em arquitetura Lakehouse para monitoramento do desempenho de uma carteira de crédito simulada, risco de crédito e inadimplência.

Este projeto foi desenvolvido com o objetivo de demonstrar competências modernas end-to-end em Data Engineering, Analytics Engineering e Business Intelligence, utilizando uma arquitetura Lakehouse-Medallion (Bronze, Silver e Gold) implementada em Databricks com PySpark, Delta Lake, SQL e Power BI.

Os dados utilizados foram gerados sinteticamente para simular o ambiente operacional de uma fintech ou instituição financeira brasileira, contendo informações de clientes, contratos de crédito, scores de risco e pagamentos. O dataset foi propositalmente criado com inconsistências de nomenclatura, formatos e qualidade de dados para reproduzir desafios reais encontrados em projetos corporativos.

Objetivos do Projeto
Construir um pipeline de dados completo utilizando arquitetura Lakehouse.
Demonstrar processos de ingestão, tratamento, padronização e enriquecimento de dados.
Implementar boas práticas de modelagem dimensional para Analytics.
Disponibilizar indicadores de negócio voltados para crédito e risco.
Demonstrar integração entre Databricks e Power BI.

## Credit Risk Lakehouse Architecture:

<img width="757" height="751" alt="DataBricks_Arquitetura_Medalhão drawio" src="https://github.com/user-attachments/assets/92591626-c138-4486-83ad-271dfb3690fd" />



Dados Brutos (CSV) Bucket - S3   
        
        │
        ▼
        
 Bronze Layer
(Ingestão dos dados)

       │
       ▼
        
 Silver Layer
(Limpeza, padronização,
regras de qualidade)
        
        │
        ▼
        
 Gold Layer
(Modelo dimensional
e KPIs de negócio)
        
        │
        ▼
        
 Power BI
(Dashboards analíticos)


## Bronze Layer - Automated Ingestion

A camada Bronze foi implementada utilizando o recurso **Data Ingestion** do Databricks.

Em vez de notebooks manuais, a ingestão foi configurada pela interface do Databricks para monitorar diretórios no Amazon S3 e criar/atualizar tabelas Delta automaticamente conforme novos arquivos CSV são adicionados.

### Fontes monitoradas

| Origem S3 | Tabela Bronze |
|---|---|
| `s3://.../s3-databricks-integracao/dev-risk-credito-contratos/` | `bronze.fact_contratos_raw_s3` |
| `s3://.../s3-databricks-integracao/dev-risk-credito-parcelas/` | `bronze.fact_parcelas_raw_s3` |
| `s3://.../s3-databricks-integracao/dev-risk-credito-pagamentos/` | `bronze.fact_pagamentos_raw_s3` |
| `s3://.../s3-databricks-integracao/dev-risk-credito-dim-cliente/` | `bronze.dim_clinte_raw_s3` |
| `s3://.../s3-databricks-integracao/dev-risk-credito-dim-produto-credito/` | `bronze.dim_produto_credito_raw_s3` |
| `s3://.../s3-databricks-integracao/dev-risk-credito-dim-score/` | `bronze.dim_score_raw_s3` |

### Características

- Ingestão incremental de novos arquivos
- Criação de tabelas Delta
- Preservação dos dados brutos
- Monitoramento de diretórios no S3
- Separação entre arquivos históricos e arquivos incrementais


## Tecnologias Utilizadas:

Python;

PySpark;

Databricks;

Delta Lake;

SQL;

Power BI;

GitHub.

## Modelo de Dados:

### Dimensões

Cliente;

Produto de Crédito;

Score de Risco;

Tempo;

## Fatos

- Contratos de Crédito;
- Parcelas;
- Pagamentos.

## Perguntas de Negócio Respondidas


#### V1 - Plataforma + Dashboard Executive Overview

<img width="1538" height="860" alt="image" src="https://github.com/user-attachments/assets/c5597447-f468-42a9-81f1-bb895c9d986a" />


#### Link do dashboard: https://app.powerbi.com/view?r=eyJrIjoiMThkZDhiNTMtYWY4ZS00ZmI3LTk2YmMtMTBjNDAwZTk0MGI0IiwidCI6ImZhYmM4MmMxLTkyZGItNDU0Ni05YzUyLTJmNjUzNjE2YjY0OCJ9
Perguntas respondidas:
- A carteira de crédito está crescendo?
- Os novos contratos estão sendo originados com valores maiores ou menores?
- Qual o volume total de crédito concedido no período?
- O valor efetivamente recebido está de acordo com o valor esperado?
- Qual o montante que ainda permanece em aberto?
- A inadimplência está aumentando ao longo do tempo?
- A taxa de default está melhorando ou piorando?
- Como os principais indicadores da carteira evoluem mês a mês?

#### V2 — Risk Analytics

Credit Risk Analysis - Módulo de Análise de Risco

Perguntas respondidas:

- Qual faixa de score concentra maior risco?
- Qual score possui maior inadimplência?
- Qual score apresenta maior índice de recebimento?
- Onde está concentrado o saldo em aberto?


#### V3 — Product Performance

Perguntas respondidas:

- Qual produto gera maior receita?
- Qual produto possui maior inadimplência?
- Qual produto possui melhor índice de recebimento?
- Ticket médio por modalidade.

#### V4 - Cohort Analysis (Safras)

Perguntas respondidas:

- As novas safras são melhores?
- A inadimplência está aumentando nas novas originações?
- Qual safra possui maior saldo em aberto?
- Evolução das safras.


## Destaques Técnicos
Implementação da arquitetura Medallion (Bronze, Silver e Gold)

Tratamento de dados inconsistentes na camada Silver

Padronização de formatos de datas, moedas e categorias

Construção de modelo dimensional Star Schema

Criação de métricas de risco e crédito para consumo analítico

Desenvolvimento de dashboards executivos e operacionais no Power BI

## Cenário Simulado

O projeto representa uma fintech fictícia chamada CrediVision, especializada em crédito para pessoas físicas. O ambiente foi modelado para reproduzir desafios comuns do mercado financeiro, incluindo:

Diferentes modalidades de crédito;

Scores de risco;

Atrasos de pagamento;

Inadimplência;

Qualidade de dados heterogênea;

Necessidade de governança e rastreabilidade;

## Competências Demonstradas

Engenharia de Dados;

Analytics Engineering;

Data Quality;

Modelagem Dimensional;

Business Intelligence;

Governança de Dados;

Desenvolvimento de Pipelines de Dados.
