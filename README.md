NovaSaaS Analytics Platform
Business Intelligence para uma empresa SaaS fictícia, com foco em receita, operação, churn e retenção.
O projeto simula uma entrega real de BI: dados modelados, medidas DAX, validações e dashboards executivos construídos para apoiar decisão de negócio.
<br>
Dashboard
Visão Executiva
<img src="images/01_visao_executiva.png" alt="Dashboard Visão Executiva" width="100%">
<br>
Analytics Operacional
<img src="images/02_analytics_operacional.png" alt="Dashboard Analytics Operacional" width="100%">
<br>
Churn & Retenção
<img src="images/03_churn_retencao.png" alt="Dashboard Churn e Retenção" width="100%">
<br>
Objetivo
Acompanhar a saúde de uma operação SaaS a partir de três frentes:
Frente	Pergunta de negócio
Receita	A empresa está crescendo de forma sustentável?
Operação	A execução está saudável ou existem gargalos?
Retenção	Quais clientes e segmentos precisam de atenção?
<br>
Principais indicadores
Categoria	Indicadores
Receita	Receita recebida, MRR, ARR, ARPU
Clientes	Clientes ativos, novos clientes, clientes perdidos
Churn	Taxa de churn, taxa de retenção, MRR em risco
Operação	Transações, taxa de sucesso, backlog, exceções
<br>
Modelo de dados
O projeto foi estruturado em um modelo analítico com dimensões e fatos.
```bash
data/
├── csv_model/
│   ├── dim_customer.csv
│   ├── dim_date.csv
│   ├── dim_empresa.csv
│   ├── dim_plan.csv
│   ├── dim_product.csv
│   ├── dim_region.csv
│   ├── dim_seller.csv
│   ├── fact_event.csv
│   ├── fact_payment.csv
│   ├── fact_subscription.csv
│   └── fact_usage.csv
│
└── excel/
    └── NovaSaaS_PowerBI_Dashboard_Data.xlsx
```
<br>
Estrutura do repositório
```bash
.
├── data/       # Dados usados no projeto
├── dax/        # Medidas DAX
├── images/     # Prints finais do dashboard
├── qa/         # Resultados esperados e validações
└── README.md
```
<br>
Medidas DAX
As medidas utilizadas no dashboard estão em:
```bash
dax/NovaSaaS_DAX_Measures.dax
```
Exemplo:
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
<br>
Validações
A pasta `qa/` contém arquivos de conferência para validar se os números do Power BI estão corretos.
Foram considerados pontos como:
receita apenas com pagamentos confirmados;
conferência dos principais KPIs;
evolução mensal de MRR;
receita por plano e região;
performance por plano;
clientes no ranking;
consistência de status e relacionamentos.
<br>
Resultados esperados
Indicador	Valor
Receita Recebida	R$ 41,9 mi
MRR Atual	R$ 3,4 mi
ARR	R$ 41,1 mi
Clientes Ativos	8.708
Churn Mensal	1,30%
ARPU	R$ 393,80
<br>
Ferramentas
Power BI
DAX
Excel
CSV
GitHub
<br>
Sobre
Projeto fictício criado para portfólio, simulando uma entrega de BI para uma empresa SaaS.
