<div align="center">

# NovaSaaS Analytics Platform

### Plataforma de BI para análise de receita, operação, churn e retenção em uma empresa SaaS fictícia

<br>

![Power BI](https://img.shields.io/badge/Power%20BI-Data%20Visualization-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-1F4E79?style=flat-square)
![Analytics](https://img.shields.io/badge/Analytics-SaaS%20Metrics-0057B8?style=flat-square)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-2E7D32?style=flat-square)

</div>

---

## Sobre o projeto

O **NovaSaaS Analytics Platform** é um projeto de Business Intelligence desenvolvido para simular uma operação SaaS com acompanhamento de receita, clientes, operação, churn e retenção.

A proposta foi construir um case com visão de negócio e estrutura analítica, passando por:

- organização dos dados;
- modelagem analítica;
- criação de medidas DAX;
- validação dos principais indicadores;
- construção de dashboards para tomada de decisão.

O projeto foi pensado para responder perguntas comuns em empresas SaaS:

| Pergunta | Indicadores analisados |
|---|---|
| A receita está crescendo de forma saudável? | Receita, MRR, ARR, ARPU |
| Quais planos sustentam o faturamento? | Receita por plano, MRR por plano |
| A operação está eficiente? | Transações, backlog, taxa de sucesso |
| O churn está controlado? | Churn mensal, retenção, clientes em risco |
| Onde priorizar ações comerciais? | Segmentos, regiões, clientes e planos |

---

## Dashboards

### 1. Visão Executiva

Visão consolidada dos principais indicadores de receita, base de clientes e crescimento.

<img src="images/01_visao_executiva.png" alt="Dashboard Visão Executiva" width="100%">

**Principais análises:**

- Receita recebida;
- MRR atual;
- ARR;
- clientes ativos;
- churn mensal;
- ARPU;
- receita por plano;
- receita por região;
- performance por plano;
- top clientes por MRR.

---

### 2. Analytics Operacional

Monitoramento da execução operacional, volume transacional e exceções.

<img src="images/02_analytics_operacional.png" alt="Dashboard Analytics Operacional" width="100%">

**Principais análises:**

- total de transações;
- taxa de sucesso;
- tempo médio de ciclo;
- backlog;
- exceções;
- distribuição por status;
- ranking de unidades;
- registros detalhados.

---

### 3. Churn e Retenção

Análise de perda de clientes, retenção, clientes em risco e oportunidades de ação.

<img src="images/03_churn_retencao.png" alt="Dashboard Churn e Retenção" width="100%">

**Principais análises:**

- clientes totais;
- novos clientes;
- clientes perdidos;
- taxa de churn;
- taxa de retenção;
- MRR em risco;
- comparação por segmento;
- clientes com maior risco;
- sugestões de retenção e upsell.

---

## Indicadores principais

| Área | Indicador | Descrição |
|---|---|---|
| Receita | Receita Recebida | Soma dos pagamentos confirmados |
| Receita | MRR Atual | Receita recorrente mensal ativa |
| Receita | ARR | MRR anualizado |
| Receita | ARPU | Receita média por cliente ativo |
| Clientes | Clientes Ativos | Clientes com assinatura ativa |
| Churn | Churn Mensal | Percentual de clientes perdidos no período |
| Retenção | Taxa de Retenção | Percentual de clientes mantidos |
| Operação | Taxa de Sucesso | Percentual de transações concluídas |
| Operação | Backlog | Volume de itens pendentes |
| Risco | MRR em Risco | Receita associada a clientes com maior risco de churn |

---

## Estrutura do repositório

```bash
.
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
├── images/
│   ├── 01_visao_executiva.png
│   ├── 02_analytics_operacional.png
│   └── 03_churn_retencao.png
│
├── qa/
│   ├── expected_kpis.csv
│   ├── expected_mrr_trend.csv
│   ├── expected_revenue_by_plan.csv
│   ├── expected_revenue_by_region.csv
│   ├── expected_plan_performance.csv
│   └── data_quality_expected_results.csv
│
└── README.md
```

---

## Modelo de dados

O projeto foi organizado em uma estrutura analítica com dimensões e fatos.

### Dimensões

| Tabela | Descrição |
|---|---|
| `dim_customer` | Cadastro e atributos dos clientes |
| `dim_empresa` | Informações das empresas |
| `dim_date` | Calendário analítico |
| `dim_plan` | Planos comerciais |
| `dim_product` | Produtos e funcionalidades |
| `dim_region` | Localização e região |
| `dim_seller` | Vendedores e responsáveis comerciais |

### Fatos

| Tabela | Descrição |
|---|---|
| `fact_payment` | Pagamentos, status financeiro e receita |
| `fact_subscription` | Assinaturas, ativações e cancelamentos |
| `fact_usage` | Uso da plataforma e engajamento |
| `fact_event` | Eventos operacionais e transacionais |

---

## Medidas DAX

As medidas utilizadas no dashboard estão no arquivo:

```bash
dax/NovaSaaS_DAX_Measures.dax
```

Exemplos:

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

---

## Validação dos resultados

A pasta `qa/` contém arquivos com resultados esperados para conferir os principais números do Power BI.

Validações consideradas:

- receita calculada apenas com pagamentos confirmados;
- consistência dos KPIs principais;
- evolução mensal de MRR;
- receita por plano;
- receita por região;
- performance por plano;
- status de pagamento;
- clientes no ranking;
- checks básicos de qualidade dos dados.

### Resultados esperados

| Indicador | Valor esperado |
|---|---:|
| Receita Recebida | R$ 41,9 mi |
| MRR Atual | R$ 3,4 mi |
| ARR | R$ 41,1 mi |
| Clientes Ativos | 8.708 |
| Churn Mensal | 1,30% |
| ARPU | R$ 393,80 |

---

## Principais insights

- Os planos **Enterprise** e **Pro** concentram a maior parte da receita.
- O MRR apresenta trajetória consistente de crescimento no período analisado.
- A região Sudeste possui maior participação na receita total.
- O plano Starter apresenta maior risco relativo de churn.
- Clientes com maior engajamento tendem a apresentar melhor retenção.
- A operação teve crescimento de volume com backlog em queda.
- Clientes com score de risco elevado devem ser priorizados em ações de retenção.

---

## Ferramentas utilizadas

| Ferramenta | Uso |
|---|---|
| Power BI | Construção dos dashboards |
| DAX | Criação das medidas |
| Excel | Apoio e conferência dos dados |
| CSV | Estruturação das tabelas |
| GitHub | Documentação e versionamento |

---

## Próximos passos

Melhorias futuras possíveis:

- criar pipeline de atualização dos dados;
- adicionar camada SQL;
- documentar a linhagem dos indicadores;
- publicar versão interativa no Power BI Service;
- incluir testes automatizados de qualidade dos dados.

---

<div align="center">

**Projeto fictício de portfólio, criado para simular uma entrega de BI em contexto SaaS.**

</div>
