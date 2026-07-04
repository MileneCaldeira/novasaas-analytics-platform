NovaSaaS Analytics Platform
Projeto de Business Intelligence para acompanhamento de receita, operação, churn e retenção de uma empresa SaaS fictícia.
A proposta foi construir um case de ponta a ponta, simulando uma entrega real de BI: dados estruturados, modelo analítico, medidas DAX, validações e dashboards executivos.
---
Contexto
Empresas SaaS precisam acompanhar mais do que receita total.  
Para entender se o crescimento é saudável, é necessário olhar para:
receita recorrente;
evolução de MRR;
clientes ativos;
churn;
retenção;
desempenho operacional;
clientes em risco;
planos e regiões com maior impacto no resultado.
Este projeto organiza esses indicadores em três visões principais.
---
Dashboards
1. Visão Executiva
Página voltada para leitura rápida dos principais indicadores do negócio.
![Visão Executiva](images/01_visao_executiva.png)
Indicadores e análises:
Receita recebida;
MRR atual;
ARR;
clientes ativos;
churn mensal;
ARPU;
receita por plano;
receita por região;
principais clientes por MRR.
---
2. Analytics Operacional
Página focada em monitoramento de execução e performance dos processos.
![Analytics Operacional](images/02_analytics_operacional.png)
Indicadores e análises:
volume de transações;
taxa de sucesso;
tempo médio de ciclo;
backlog;
exceções;
distribuição por status;
ranking de unidades;
registros detalhados.
---
3. Churn e Retenção
Página voltada para análise de perda de clientes, retenção e priorização de ações.
![Churn e Retenção](images/03_churn_retencao.png)
Indicadores e análises:
clientes totais;
novos clientes;
clientes perdidos;
taxa de churn;
taxa de retenção;
MRR em risco;
comparação por segmento;
clientes com maior risco;
sugestões de ação.
---
Estrutura do projeto
```bash
.
├── data/
│   ├── csv_model/
│   └── excel/
├── dax/
├── images/
├── qa/
└── README.md
```
`data/csv_model`
Tabelas utilizadas para montar o modelo no Power BI.
Inclui dimensões e fatos, como:
clientes;
datas;
empresas;
planos;
produtos;
regiões;
vendedores;
pagamentos;
assinaturas;
eventos;
uso da plataforma.
`dax`
Arquivo com as medidas utilizadas no dashboard.
`qa`
Arquivos com resultados esperados para conferência dos KPIs e visuais.
`images`
Prints finais das páginas do dashboard.
---
Modelo de dados
O projeto foi organizado em uma estrutura próxima de um modelo estrela.
Dimensões principais:
Tabela	Descrição
`dim_customer`	Dados dos clientes
`dim_empresa`	Informações das empresas
`dim_date`	Calendário analítico
`dim_plan`	Planos comerciais
`dim_product`	Produtos e funcionalidades
`dim_region`	Regiões
`dim_seller`	Vendedores
Fatos principais:
Tabela	Descrição
`fact_payment`	Pagamentos e receita
`fact_subscription`	Assinaturas e cancelamentos
`fact_usage`	Uso da plataforma
`fact_event`	Eventos operacionais
---
Principais métricas
Algumas das medidas utilizadas no projeto:
Métrica	Descrição
Receita Recebida	Soma dos pagamentos confirmados
MRR Atual	Receita recorrente mensal da base ativa
ARR	MRR anualizado
Clientes Ativos	Clientes ativos no período
Churn Mensal	Clientes perdidos sobre base anterior
ARPU	Receita média por cliente
MRR em Risco	Receita associada a clientes com maior risco de churn
Taxa de Sucesso	Percentual de eventos concluídos com sucesso
---
Exemplos de DAX
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
Validações
Para reduzir risco de inconsistência, o projeto inclui arquivos de validação na pasta `qa`.
Alguns pontos conferidos:
total dos principais KPIs;
receita por plano;
receita por região;
evolução mensal de MRR;
performance por plano;
clientes no ranking;
status de pagamento;
checks de qualidade dos dados.
Exemplos de riscos considerados:
duplicidade de clientes;
pagamentos negativos;
clientes sem assinatura;
relacionamento incorreto entre fatos e dimensões;
uso de status de pagamento errado para calcular receita;
cálculo de churn usando base incorreta.
---
Resultados esperados
Alguns números utilizados como referência para validação:
Indicador	Valor esperado
Receita Recebida	R$ 41,9 mi
MRR Atual	R$ 3,4 mi
ARR	R$ 41,1 mi
Clientes Ativos	8.708
Churn Mensal	1,30%
ARPU	R$ 393,80
---
Principais aprendizados
Este projeto reforça pontos importantes em uma entrega de BI:
separar métrica financeira de métrica operacional;
validar granularidade antes de criar medidas;
evitar relacionamento muitos-para-muitos sem necessidade;
conferir os KPIs com bases auxiliares;
documentar regra de negócio;
construir dashboards com foco em decisão, não apenas visual.
---
Ferramentas utilizadas
Power BI
DAX
CSV
Excel
Markdown
GitHub
---
Observação
Os dados são fictícios e foram estruturados para simular um cenário realista de uma empresa SaaS.
