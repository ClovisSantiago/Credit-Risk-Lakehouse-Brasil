# Credit-Risk-Lakehouse-Brasil
Projeto de Engenharia e Análise de Dados baseado em arquitetura Lakehouse para monitoramento de risco de crédito, inadimplência e desempenho de uma carteira de crédito simulada.

Este projeto foi desenvolvido com o objetivo de demonstrar competências modernas em Data Engineering, Analytics Engineering e Business Intelligence, utilizando uma arquitetura Medallion (Bronze, Silver e Gold) implementada em Databricks com PySpark, Delta Lake e Power BI.

Os dados utilizados foram gerados sinteticamente para simular o ambiente operacional de uma fintech ou instituição financeira brasileira, contendo informações de clientes, contratos de crédito, scores de risco e pagamentos. O dataset foi propositalmente criado com inconsistências de nomenclatura, formatos e qualidade de dados para reproduzir desafios reais encontrados em projetos corporativos.

Objetivos do Projeto
Construir um pipeline de dados completo utilizando arquitetura Lakehouse.
Demonstrar processos de ingestão, tratamento, padronização e enriquecimento de dados.
Implementar boas práticas de modelagem dimensional para Analytics.
Disponibilizar indicadores de negócio voltados para crédito e risco.
Demonstrar integração entre Databricks e Power BI.

## Arquitetura:

<img width="1797" height="1521" alt="image" src="https://github.com/user-attachments/assets/9b7763ca-f85b-451f-8414-64f6752fb571" />



Dados Brutos (CSV)   
        
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

Contratos de Crédito;

Pagamentos.

## Indicadores Disponíveis

Carteira de Crédito

Valor total contratado

Valor médio dos contratos

Evolução da carteira

Risco

Taxa de inadimplência

Contratos em atraso

Inadimplência por faixa de score

Inadimplência por região

## Operação
Contratos emitidos

Pagamentos recebidos

Dias médios de atraso

Recuperação de crédito

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
