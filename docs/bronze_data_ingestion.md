# Bronze Data Ingestion

## Objetivo

Carregar arquivos CSV brutos armazenados no Amazon S3 para tabelas Delta na camada Bronze do Databricks.

## Abordagem

A ingestão foi configurada usando a opção **Data Ingestion** do Databricks, sem uso de notebook customizado.

Essa escolha simula um cenário corporativo em que pipelines de ingestão são configurados de forma gerenciada, com monitoramento automático de novos arquivos no bucket.

## Fluxo


Amazon S3 -> Databricks Data Ingestion -> Bronze Delta Tables

## Diretórios de origem
- s3-databricks-integracao/dev-risk-credito-contratos/
- s3-databricks-integracao/dev-risk-credito-parcelas/
- s3-databricks-integracao/dev-risk-credito-pagamentos/
- s3-databricks-integracao/dev-risk-credito-dim-cliente/
- s3-databricks-integracao/dev-risk-credito-dim-produto-credito/
- s3-databricks-integracao/dev-risk-credito-dim-score/

## Tabelas de destino
- bronze.fact_contratos_raw_s3
- bronze.fact_parcelas_raw_s3
- bronze.fact_pagamentos_raw_s3
- bronze.dim_cliente_raw_s3
- bronze.dim_produto_credito_raw_s3
- bronze.dim_score_raw_s3