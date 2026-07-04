NovaSaaS Analytics Platform
> Plataforma de Business Intelligence para análise de clientes, receita, operação, churn e retenção em uma empresa SaaS fictícia.
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-0B5CAD?style=for-the-badge)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-Star%20Schema-1F7A8C?style=for-the-badge)
![Business Intelligence](https://img.shields.io/badge/BI-Customer%20Analytics-0A66C2?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-2E7D32?style=for-the-badge)
---
1. Visão geral
O NovaSaaS Analytics Platform é um projeto de Business Intelligence desenvolvido para simular um ambiente real de uma empresa SaaS, com foco em:
acompanhamento de receita;
análise de MRR e ARR;
clientes ativos;
churn e retenção;
performance operacional;
qualidade e validação dos dados;
construção de indicadores executivos e operacionais.
A proposta do projeto não é apenas criar um dashboard visual, mas estruturar um case completo de BI, com dados modelados, medidas DAX, camada de validação, documentação técnica e visuais finais para apresentação em portfólio.
---
2. Objetivo de negócio
Empresas SaaS precisam acompanhar continuamente se estão crescendo de forma saudável.
Este projeto responde perguntas como:
A receita recorrente está crescendo?
Quais planos sustentam o maior volume de MRR?
Quais regiões concentram receita e clientes?
O churn está controlado?
Quais segmentos apresentam maior risco de cancelamento?
A operação está performando bem?
Existem gargalos, backlog ou exceções relevantes?
Quais clientes devem ser priorizados em ações de retenção?
---
3. Demonstração do dashboard
Página 1 — Visão Executiva
A página executiva consolida os principais indicadores de receita, base de clientes e crescimento.
![Visão Executiva](images/01_visao_executiva.png)
Principais análises:
Receita recebida;
MRR atual;
ARR;
Clientes ativos;
Churn mensal;
ARPU;
Receita por plano;
Receita por região;
Top clientes por MRR;
Performance por plano.
---
Página 2 — Analytics Operacional
A página operacional acompanha volume transacional, SLA, backlog e exceções.
![Analytics Operacional](images/02_analytics_operacional.png)
Principais análises:
Total de transações;
Taxa de sucesso;
Tempo médio de ciclo;
Backlog;
Exceções;
Distribuição por status;
Ranking de unidades;
Registros detalhados.
---
Página 3 — Churn & Retenção
A página de churn e retenção monitora saúde da base, risco de cancelamento e oportunidades de ação.
![Churn e Retenção](images/03_churn_retencao.png)
Principais análises:
Clientes totais;
Novos clientes;
Clientes perdidos;
Taxa de churn;
Taxa de retenção;
MRR em risco;
Comparação por segmento;
Clientes em risco;
Sugestões de ação.
---
4. Stack utilizada
Camada	Tecnologia
Visualização	Power BI
Modelagem analítica	Star Schema
Métricas	DAX
Dados	CSV / Excel
Documentação	Markdown
Validação	Arquivos QA com resultados esperados
Versionamento	Git / GitHub
---
5. Estrutura do projeto
```bash
NovaSaaS_Analytics_Platform/
├── data/
│   ├── csv_model/
│   │   ├── dim_customer.csv
│   │   ├── dim_date.csv
│   │   ├── dim_empresa.csv
│   │   ├── dim_plan.csv
│   │   ├── dim_product.csv
│   │   ├── dim_region.csv
│   │   ├── dim_seller.csv
│   │   ├── fact_event.csv
│   │   ├── fact_payment.csv
│   │   ├── fact_subscription.csv
│   │   └── fact_usage.csv
│   │
│   └── excel/
│       └── NovaSaaS_PowerBI_Dashboard_Data.xlsx
│
├── dax/
│   └── NovaSaaS_DAX_Measures.dax
│
├── qa/
│   ├── data_quality_expected_results.csv
│   ├── expected_engagement_retention.csv
│   ├── expected_event_type.csv
│   ├── expected_kpis.csv
│   ├── expected_mrr_trend.csv
│   ├── expected_payment_status.csv
│   ├── expected_plan_performance.csv
│   ├── expected_product_events.csv
│   ├── expected_region_month.csv
│   ├── expected_results.json
│   ├── expected_revenue_by_plan.csv
│   ├── expected_revenue_by_region.csv
│   └── expected_top_customers.csv
│
├── images/
│   ├── 01_visao_executiva.png
│   ├── 02_analytics_operacional.png
│   └── 03_churn_retencao.png
│
└── README.md
```
---
6. Modelagem dos dados
O projeto foi estruturado utilizando modelagem dimensional em Star Schema.
A modelagem separa as tabelas em:
dimensões, que descrevem entidades de negócio;
fatos, que armazenam eventos mensuráveis.
Dimensões
Tabela	Finalidade
`dim_customer`	Informações dos clientes
`dim_empresa`	Cadastro e atributos empresariais
`dim_date`	Calendário analítico
`dim_plan`	Planos e características comerciais
`dim_product`	Produtos e funcionalidades
`dim_region`	Localização e região
`dim_seller`	Vendedores e responsáveis comerciais
Fatos
Tabela	Finalidade
`fact_payment`	Pagamentos, receita e status financeiro
`fact_subscription`	Assinaturas, planos, ativações e cancelamentos
`fact_usage`	Uso da plataforma e engajamento
`fact_event`	Eventos operacionais e transacionais
---
7. Principais KPIs
Receita e crescimento
Indicador	Descrição
Receita Recebida	Soma dos pagamentos efetivamente recebidos
MRR Atual	Receita recorrente mensal ativa
ARR	MRR anualizado
ARPU	Receita média por cliente ativo
Receita por Plano	Distribuição da receita entre planos
Receita por Região	Distribuição geográfica da receita
Clientes e retenção
Indicador	Descrição
Clientes Ativos	Clientes com assinatura ativa
Clientes Perdidos	Clientes cancelados no período
Taxa de Churn	Percentual de clientes perdidos
Taxa de Retenção	Percentual de clientes mantidos
MRR em Risco	Receita potencialmente exposta a churn
Clientes em Risco	Clientes com maior propensão de cancelamento
Operação
Indicador	Descrição
Total de Transações	Volume operacional processado
Taxa de Sucesso	Percentual de operações concluídas
Tempo Médio de Ciclo	Tempo médio de execução dos processos
Backlog	Volume de itens pendentes
Exceções	Erros, falhas ou inconsistências operacionais
---
8. Medidas DAX
As medidas principais estão no arquivo:
```bash
dax/NovaSaaS_DAX_Measures.dax
```
Exemplos de métricas implementadas:
```DAX
Revenue Received =
CALCULATE (
    SUM ( fact_payment[amount] ),
    fact_payment[payment_status] = "Paid"
)
```
```DAX
ARR Run Rate =
[MRR Current] * 12
```
```DAX
ARPU =
DIVIDE (
    [MRR Current],
    [Active Customers]
)
```
```DAX
Monthly Churn Rate =
DIVIDE (
    [Churned Customers],
    [Customers Previous Month]
)
```
---
9. Validação dos dados
O projeto inclui uma camada de validação para garantir consistência entre modelo, medidas e visualização.
Arquivos de validação:
```bash
qa/
├── expected_kpis.csv
├── expected_mrr_trend.csv
├── expected_revenue_by_plan.csv
├── expected_revenue_by_region.csv
├── expected_plan_performance.csv
├── expected_top_customers.csv
└── data_quality_expected_results.csv
```
Exemplos de validações
Validação	Objetivo
Clientes duplicados	Evitar multiplicação de linhas
Pagamentos negativos	Identificar inconsistência financeira
Plano inexistente	Verificar integridade referencial
Cliente sem assinatura	Validar relacionamento entre dimensões e fatos
Datas inválidas	Garantir coerência temporal
Total esperado por KPI	Conferir se o Power BI está calculando corretamente
---
10. Resultados esperados
Alguns números esperados para conferência da página executiva:
Métrica	Valor esperado
Receita Recebida	R$ 41,9 mi
MRR Atual	R$ 3,4 mi
ARR	R$ 41,1 mi
Clientes Ativos	8.708
Churn Mensal	1,30%
ARPU	R$ 393,80
Esses valores podem ser conferidos nos arquivos de QA e no Excel de apoio.
---
11. Insights de negócio
Alguns insights identificados no case:
Os planos Enterprise e Pro concentram a maior parte da receita.
O MRR mantém trajetória consistente de crescimento ao longo do período analisado.
A região Sudeste representa a maior participação da receita total.
O plano Starter apresenta maior risco relativo de churn.
Clientes com maior engajamento tendem a apresentar maior retenção.
A operação apresentou crescimento de volume sem aumento proporcional de exceções.
A redução de backlog indica melhora na capacidade operacional.
Clientes com score de risco elevado devem ser priorizados em ações de retenção.
O ARPU é mais alto nos planos corporativos.
A análise combinada de receita, operação e churn permite priorização mais assertiva.
---
12. Como reproduzir o projeto
Clone este repositório:
```bash
git clone https://github.com/seu-usuario/novasaas-analytics-platform.git
```
Abra o Power BI Desktop.
Importe os arquivos da pasta:
```bash
data/csv_model/
```
Configure os relacionamentos do modelo estrela.
Copie as medidas DAX do arquivo:
```bash
dax/NovaSaaS_DAX_Measures.dax
```
Valide os resultados com os arquivos da pasta:
```bash
qa/
```
Compare os resultados finais com as imagens em:
```bash
images/
```
---
13. Aprendizados do projeto
Este projeto reforça competências importantes para uma atuação em BI e Analytics:
construção de indicadores executivos;
análise de receita recorrente;
entendimento de métricas SaaS;
modelagem dimensional;
criação de medidas DAX;
validação de dados;
documentação técnica;
organização de projeto para portfólio;
comunicação visual de resultados.
---
14. Próximas melhorias
Possíveis evoluções futuras:
criação de pipeline em Python para geração e atualização automática dos dados;
inclusão de camada SQL;
criação de views analíticas;
publicação do relatório no Power BI Service;
integração com API simulada;
criação de documentação de linhagem de dados;
inclusão de testes automatizados de data quality.
---
15. Sobre o projeto
Este é um projeto fictício de portfólio, com dados simulados e estrutura inspirada em problemas reais de empresas SaaS.
O foco é demonstrar capacidade de transformar dados em indicadores úteis para tomada de decisão.
