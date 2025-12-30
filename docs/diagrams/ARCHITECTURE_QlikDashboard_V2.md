# QlikDashboard – Arquitetura v2 (Visão Pública)

## Visão Geral

Esta versão **v2** do diagrama explicita os **módulos funcionais principais**
do sistema, mantendo o mesmo desenho técnico da versão anterior,
apenas com melhor clareza de escopo e responsabilidades.

---

## Diagrama de Arquitetura (Mermaid)

```mermaid
flowchart TB

    subgraph UI["Dashboard Web"]
        A1["Comercial & Performance"]
        A2["Financeiro & Fluxo de Caixa"]
        A3["Previsões Inteligentes"]
    end

    subgraph FE["Frontend"]
        FE1["Next.js + React + TypeScript"]
    end

    subgraph API["Backend / API"]
        API1["Next.js API Routes"]
        API2["Camada de Serviços"]
    end

    subgraph DB["Camada de Dados"]
        DB1["PostgreSQL"]
        DB2["Views & Funções SQL"]
    end

    subgraph EXT["Fontes Externas (opcional)"]
        EXT1["Clima (Open-Meteo)"]
        EXT2["Câmbio (USD/BRL – Bacen)"]
        EXT3["IPCA / SELIC – Bacen"]
    end

    UI --> FE
    FE --> API
    API --> DB
    DB --> API

    EXT --> API
```

---

## Componentes Representados

### Frontend
- Aplicação web em **Next.js**
- Camada única de UI consumindo APIs internas
- Separação lógica por domínio:
  - Comercial
  - Financeiro
  - Forecast

### Backend / API
- API Routes do Next.js
- Camada de serviços para:
  - Comercial (vendas, budget, performance)
  - Financeiro (CR/CP, fluxo, investimentos, empréstimos)
  - Forecast (consumo de previsões e agregações)

### Camada de Dados
- PostgreSQL como fonte única de verdade
- Uso intensivo de:
  - Views para consolidação
  - Funções SQL para projeções e cálculos financeiros

### Fontes Externas
- Variáveis macroeconômicas e climáticas
- Utilizadas **somente na geração de previsões**
- Pipelines de ML não fazem parte deste repositório público

---

## Observação Importante

Este diagrama representa **a arquitetura lógica e funcional** do sistema.
Detalhes de regras financeiras, fórmulas, modelos de ML e pipelines
são intencionalmente omitidos por se tratarem de conhecimento proprietário.

---

**Status:** arquitetura validada em produção  
**Uso:** documentação pública (LinkedIn / Portfólio)
