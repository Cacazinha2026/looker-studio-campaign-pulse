# 🔄 Fluxo de Dados e Arquitetura | Campaign Pulse

## 1. Visão geral

O projeto Campaign Pulse utiliza uma estrutura de integração entre Google Sheets e Google Looker Studio para organizar, calcular e visualizar indicadores de desempenho de campanhas digitais.

A arquitetura foi desenvolvida para permitir o acompanhamento de resultados, investimentos e indicadores operacionais em um dashboard gerencial.

## 2. Arquitetura do projeto

O fluxo de dados é composto por três etapas principais:

### Etapa 1 — Preparação e organização dos dados

**Ferramenta:** Google Sheets

A planilha funciona como fonte de dados do projeto, contendo informações sobre:

- Data e identificação das campanhas.
- Canal e objetivo da campanha.
- Orçamento total e orçamento previsto acumulado.
- Investimento realizado.
- Impressões, cliques e conversões.
- Status operacional.

Também foram implementadas fórmulas para cálculo dos indicadores:

- CTR (Taxa de Cliques).
- CPC (Custo por Clique).
- CPA (Custo por Aquisição).
- Investimento acumulado.
- Pacing Real.
- Desvio de Pacing.
- Alerta Operacional.

### Etapa 2 — Integração e visualização

**Ferramenta:** Google Looker Studio

A planilha do Google Sheets foi conectada diretamente ao Looker Studio como fonte de dados.

O dashboard apresenta:

- Indicadores consolidados de desempenho.
- Investimento total.
- Impressões.
- Cliques.
- Conversões.
- Taxa de Cliques (CTR).
- Tabela comparativa de campanhas.
- Gráfico de investimento por campanha.
- Distribuição dos alertas operacionais.

Também foram disponibilizados filtros interativos por período e campanha.

### Etapa 3 — Análise gerencial

A camada de visualização permite acompanhar os resultados e identificar situações que merecem investigação.

Entre as possibilidades de análise estão:

- Comparação de desempenho entre campanhas.
- Acompanhamento de investimentos.
- Identificação de desvios de pacing.
- Monitoramento de alertas operacionais.
- Comparação de indicadores entre canais.

## 3. Fluxo de integração

Google Sheets → Google Looker Studio → Dashboard Gerencial → Análise de Desempenho.

A integração direta permite utilizar os dados organizados na planilha como fonte para a visualização gerencial.

## 4. Tecnologias utilizadas

| Tecnologia | Aplicação |
|---|---|
| Google Sheets | Organização dos dados e cálculos dos indicadores |
| Google Looker Studio | Conexão com a fonte e construção do dashboard |
| Fórmulas do Google Sheets | Cálculos e regras de negócio |
| Business Intelligence | Análise e acompanhamento de desempenho |

## 5. Resultado do projeto

A solução demonstra a aplicação de conceitos de Business Intelligence na organização e visualização de informações de campanhas digitais.

O projeto integra preparação de dados, cálculos de indicadores, acompanhamento operacional e visualização gerencial em um fluxo de trabalho.

## 6. Observações técnicas

- Projeto demonstrativo com dados fictícios.
- A conexão entre Google Sheets e Looker Studio é direta.
- Os cálculos documentados são realizados no Google Sheets.
- O dashboard apresenta os indicadores e visualizações desenvolvidos para o projeto.

---

**Campaign Pulse | Digital Media Intelligence**

Projeto demonstrativo de Business Intelligence — 2026.
