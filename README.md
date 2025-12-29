Commercial & Forecast Analytics

🔗 **Languages**  
- [Português 🇧🇷](#português)  
- [English 🇺🇸](#english)

---

## Português

### Visão Geral

O **SalesIQ** é um **dashboard web corporativo** desenvolvido em **React / Next.js**, inspirado no estilo do **Qlik Sense**, para visualização avançada de dados comerciais, financeiros e operacionais — agora com **previsão inteligente de vendas**.

O projeto foi criado para **centralizar indicadores críticos do negócio**, reduzir dependência de planilhas, acelerar decisões e oferecer **análises explicáveis**, inclusive para previsões.

📌 **Status:** validação final / rollout  
📌 **Tipo:** sistema corporativo interno  
📌 **Código-fonte:** privado (repositório público apenas para documentação)

---

### Problema

Antes do SalesIQ:

- Dados comerciais dispersos em múltiplas fontes  
- Dependência excessiva de planilhas manuais  
- Dificuldade de cruzar vendas, orçamento e desempenho  
- Baixa visibilidade financeira (fluxo, CR/CP, projeções)  
- Previsões pouco confiáveis ou não explicáveis  
- Alto custo de licenças e customizações em ferramentas BI tradicionais  

---

### Solução

O SalesIQ entrega:

- Dashboards web interativos no estilo Qlik Sense  
- KPIs comerciais, financeiros e operacionais centralizados  
- Comparativos de **Vendas vs Budget**  
- Análises por cliente, produto, região e responsável  
- Fluxo de caixa, contas a receber/pagar e projeções  
- **Previsão inteligente de vendas com explainability**  
- Arquitetura modular e evolutiva  

---

### Fluxos Principais

- **Comercial:** vendas, produtos, clientes, performance  
- **Previsões:** projeções inteligentes por Ano Francês  
- **Financeiro:** faturamento, fluxo de caixa, CR/CP  
- **Logística / Produção:** em evolução  

---

### Arquitetura (alto nível)

```
[ Next.js / React ]
        |
        v
[ API Routes (Next.js) ]
        |
[ PostgreSQL ]
```

---

### Stack Tecnológico

**Frontend**
- Next.js
- React 18
- TypeScript
- Tailwind CSS
- ShadCN / Radix UI

**Visualização**
- ApexCharts
- Recharts
- D3.js
- Leaflet (mapas)

**Dados**
- PostgreSQL
- Views SQL e funções agregadas

---

### Previsão Inteligente (Diferencial)

A página de **Previsões** oferece:

- Base conceitual em **Ano Francês (Set → Ago)**  
- KPIs executivos de crescimento e projeção  
- Série histórica + previsão futura  
- Intervalos de confiança (cone de incerteza)  
- Comparativos entre semestres  

#### Como a previsão funciona (Explainability)

1. **Competição de Modelos**  
   Múltiplos modelos (ex: Prophet, ARIMA, LightGBM, TFT) competem entre si.  
   O modelo com menor erro (sMAPE) é selecionado.

2. **Modo Híbrido**  
   - Modelo vencedor gera a previsão central  
   - Prophet calcula intervalos de confiança e sazonalidade  

3. **Fatores Explicáveis**  
   - Fatores sazonais mensais  
   - Fator de crescimento orgânico  
   - Metadados exibidos no dashboard  

> ⚠️ Os pipelines de ML não fazem parte deste repositório público.

---

### Segurança e Governança

- APIs isoladas por domínio funcional  
- Validações server-side  
- Controle de acesso via token no frontend  
- Dados sensíveis protegidos no banco  
- Views SQL como camada de governança de dados  

---

### Papel de Liderança Técnica

Neste projeto, fui responsável por:

- Arquitetura frontend + backend  
- Definição dos fluxos de dados e KPIs  
- Governança de dados via PostgreSQL (views/funções)  
- Estruturação da camada de previsões  
- Integração entre áreas comercial e financeira  
- Estratégia de evolução incremental  
- Entrega técnica end-to-end  

---

### Observações

- Código mantido privado por se tratar de sistema corporativo  
- Este repositório público existe apenas para **documentação técnica e apresentação profissional**  

---

## English

### Overview

**SalesIQ** is an **internal web-based analytics dashboard** built with **React / Next.js**, inspired by **Qlik Sense**, designed to centralize commercial, financial, and operational data — now enhanced with **intelligent sales forecasting**.

📌 **Status:** final validation / rollout  
📌 **Type:** internal corporate system  
📌 **Source code:** private (public repository for documentation only)

---

### Problem

Before this solution:

- Business data scattered across multiple sources  
- Heavy reliance on spreadsheets  
- Limited cross-analysis between sales and budget  
- Poor financial visibility  
- Forecasts without explainability  
- High cost of traditional BI tools  

---

### Solution

SalesIQ provides:

- Interactive BI-style dashboards  
- Centralized KPIs  
- Sales vs Budget analysis  
- Customer and product performance  
- Cash flow and financial projections  
- **Explainable intelligent forecasting**  
- Modular and scalable architecture  

---

### High-Level Architecture

```
[ Next.js / React ]
        |
        v
[ Next.js API Routes ]
        |
[ PostgreSQL ]
```

---

### Technology Stack

- Next.js / React / TypeScript  
- Tailwind CSS / ShadCN  
- ApexCharts / Recharts / D3  
- PostgreSQL  

---

### Intelligent Forecasting

- French Year based analysis (Sep → Aug)  
- Hybrid forecasting models  
- Confidence intervals  
- Seasonal and growth factor explainability  

---

### Technical Leadership

Responsibilities included:

- End-to-end architecture  
- Data governance strategy  
- Forecast explainability design  
- Business KPI modeling  
- Full technical delivery  

---

### Notes

- Source code is private due to corporate ownership  
- This repository exists for **technical documentation and professional showcase only**  
