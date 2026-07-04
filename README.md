# NovaSaaS BI — Customer, Revenue, Operations & Churn Analytics

Projeto de portfólio em **Power BI + DAX + modelagem dimensional**, criado para simular um case real de uma empresa SaaS fictícia.

O objetivo é mostrar domínio de:
- modelagem estrela;
- construção de KPIs de negócio;
- DAX;
- organização de projeto para GitHub;
- visão executiva, operacional e de churn/retenção.

---

## Visão geral do projeto

Este repositório reúne:
- **dados em CSV** para modelagem no Power BI;
- **Excel de apoio** para validação e conferência;
- **medidas DAX**;
- **documentação em Markdown**;
- **3 imagens finais** das páginas do dashboard;
- **arquivos de QA** com resultados esperados.

As três páginas do dashboard são:
1. **Visão Executiva** — foco em receita, MRR, ARR, clientes ativos, churn e ARPU.
2. **Analytics Operacional** — foco em execução, volume transacional, backlog, exceções e ranking.
3. **Churn & Retenção** — foco em retenção, churn, clientes em risco e recomendações de ação.

---

## Estrutura do repositório

```bash
NovaSaaS_BI_Portfolio_GitReady/
├── data/
│   ├── csv_model/
│   └── excel/
├── dax/
├── docs/
├── images/
├── powerbi/
│   └── theme/
├── qa/
├── README.md
└── .gitignore
```

---

## Arquivos principais

### Dados
- `data/csv_model/`: base do modelo estrela.
- `data/excel/NovaSaaS_PowerBI_Dashboard_Data.xlsx`: apoio para validação dos números.

### DAX
- `dax/NovaSaaS_DAX_Measures.dax`: medidas utilizadas no dashboard.

### Documentação
- `docs/01_POWERBI_SETUP_PASSO_A_PASSO.md`
- `docs/02_MODELAGEM_RELACIONAMENTOS.md`
- `docs/03_MEDIDAS_DAX.md`
- `docs/04_MAPEAMENTO_VISUAIS.md`
- `docs/05_RESULTADOS_ESPERADOS.md`
- `docs/06_CHECKLIST_VALIDACAO.md`
- `docs/07_RESUMO_DO_CASE.md`

### Imagens do dashboard
- `images/01_visao_executiva.png`
- `images/02_analytics_operacional.png`
- `images/03_churn_retencao.png`

### Qualidade e validação
- `qa/`: arquivos com KPIs esperados, dados esperados por visual e resultados de data quality.

---

## Páginas do dashboard

### 1) Visão Executiva
KPIs principais:
- Receita Recebida
- MRR Atual
- ARR
- Clientes Ativos
- Churn Mensal
- ARPU

Visuais:
- Tendência de MRR
- Receita por Plano
- Receita por Região
- Top Clientes por MRR
- Performance por Plano
- Insights

### 2) Analytics Operacional
KPIs principais:
- Total de Transações
- Taxa de Sucesso
- Tempo Médio de Ciclo
- Backlog
- Exceções

Visuais:
- Tendência de Transações
- Distribuição por Status
- Registros Detalhados
- Ranking de Unidades
- Notas de Ação

### 3) Churn & Retenção
KPIs principais:
- Clientes Totais
- Novos Clientes
- Clientes Perdidos
- Taxa de Churn
- Taxa de Retenção
- MRR em Risco

Visuais:
- Comparação por Segmento
- Clientes em Risco (High Score)
- Sugestões de IA / Recomendações

---

## Como usar

1. Abra o Power BI Desktop.
2. Importe os CSVs da pasta `data/csv_model/`.
3. Monte os relacionamentos conforme `docs/02_MODELAGEM_RELACIONAMENTOS.md`.
4. Importe o tema JSON em `powerbi/theme/`.
5. Crie as medidas DAX com base em `dax/NovaSaaS_DAX_Measures.dax`.
6. Use `docs/04_MAPEAMENTO_VISUAIS.md` para montar os visuais.
7. Valide os números com os arquivos em `qa/` e com o Excel de apoio.

---

## Diferenciais do case

- projeto organizado para GitHub;
- foco em layout de dashboard com coerência entre páginas;
- documentação em português;
- validação de métricas;
- dados estruturados para simular um projeto real de BI.

---

## Observação

Este projeto foi estruturado como **case de portfólio**, então as imagens finais podem ser usadas no GitHub, LinkedIn e portfólio pessoal junto com os arquivos de apoio.
