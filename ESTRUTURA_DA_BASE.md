# Estrutura da Base de Dados | Campaign Pulse

## 1. Visão geral

A base de dados do Campaign Pulse foi estruturada no Google Sheets para consolidar informações de campanhas digitais e permitir análises de desempenho, investimento e acompanhamento operacional.

A estrutura contempla informações descritivas das campanhas, métricas de desempenho e indicadores calculados por meio de fórmulas.

## 2. Granularidade dos dados

Cada registro representa o desempenho de uma campanha em uma determinada data.

Essa organização permite acompanhar a evolução dos indicadores ao longo do período e comparar os resultados entre diferentes campanhas e canais.

## 3. Organização dos campos

### 3.1 Dimensões e informações cadastrais

| Campo | Descrição |
|---|---|
| Data | Data de referência do registro |
| Campanha | Identificação da campanha digital |
| Canal | Canal de divulgação utilizado |
| Objetivo | Finalidade da campanha |
| Status_Operacional | Situação operacional da campanha |

### 3.2 Dados financeiros e de desempenho

| Campo | Descrição |
|---|---|
| Orcamento_Total | Orçamento total definido para a campanha |
| Orcamento_Previsto_Acumulado | Investimento previsto acumulado até a data |
| Investimento_Real | Valor efetivamente investido no período |
| Impressoes | Quantidade de impressões registradas |
| Cliques | Quantidade de cliques registrados |
| Conversoes | Quantidade de conversões registradas |

### 3.3 Indicadores calculados

| Campo | Descrição |
|---|---|
| CTR | Taxa de cliques em relação às impressões |
| CPC | Custo médio por clique |
| CPA | Custo por aquisição ou conversão |
| Investimento_Acumulado | Soma dos investimentos realizados até a data |
| Pacing_Real | Relação entre investimento acumulado e orçamento previsto acumulado |
| Desvio_Pacing | Diferença entre o pacing real e o valor de referência |
| Alerta_Operacional | Classificação do ritmo de investimento |

## 4. Organização lógica

A base está organizada em três grupos de informações:

- **Dimensões:** permitem identificar e segmentar campanhas, canais, objetivos e datas.
- **Métricas:** representam os valores financeiros e os resultados registrados.
- **Indicadores derivados:** são calculados a partir das métricas e utilizados no acompanhamento gerencial.

## 5. Aplicação no Business Intelligence

A estrutura permite utilizar os campos como dimensões e métricas no Google Looker Studio, possibilitando:

- Comparação entre campanhas.
- Análise de desempenho por canal.
- Acompanhamento temporal dos investimentos.
- Monitoramento dos indicadores de eficiência.
- Identificação de desvios em relação ao orçamento previsto.

## 6. Considerações técnicas

- Fonte de dados: Google Sheets.
- Integração: conexão direta com Google Looker Studio.
- Os indicadores calculados são obtidos por fórmulas na planilha.
- Os dados utilizados no projeto são fictícios e possuem finalidade demonstrativa.
- A estrutura dos campos deve ser preservada para manter a consistência da integração.

---

**Campaign Pulse | Digital Media Intelligence**

Projeto demonstrativo de Business Intelligence — 2026.
