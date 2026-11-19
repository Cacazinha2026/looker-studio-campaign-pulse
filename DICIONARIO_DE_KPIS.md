# 📘 Dicionário de KPIs e Regras de Negócio | Campaign Pulse

## 1. Objetivo

Documentar os indicadores de desempenho e controle operacional utilizados no projeto Campaign Pulse, apresentando suas definições, fórmulas aplicadas no Google Sheets e critérios de interpretação.

Os indicadores alimentam o processo de acompanhamento e análise das campanhas digitais no Google Looker Studio.

## 2. Indicadores de desempenho

### CTR — Click Through Rate

**Objetivo:** medir a proporção de cliques em relação ao total de impressões.

**Fórmula utilizada:**

```excel
=SEERRO(I2/H2;0)
```

**Interpretação:** indica o percentual de impressões que resultaram em cliques.

### CPC — Custo por Clique

**Objetivo:** identificar o custo médio de cada clique recebido pela campanha.

**Fórmula utilizada:**

```excel
=SEERRO(G2/I2;0)
```

**Interpretação:** permite acompanhar o investimento necessário para gerar tráfego por meio dos anúncios.

### CPA — Custo por Aquisição

**Objetivo:** identificar o custo médio por conversão registrada.

**Fórmula utilizada:**

```excel
=SE(J2>0;G2/J2;"")
```

**Interpretação:** permite comparar a eficiência de aquisição entre campanhas.

**Regra aplicada:** quando não existem conversões, o resultado permanece vazio, evitando apresentar um custo por aquisição inválido.

## 3. Indicadores de controle orçamentário

### Investimento acumulado

**Objetivo:** acompanhar a evolução do investimento realizado por campanha ao longo do período.

**Fórmula utilizada:**

```excel
=SOMASES($G$2:$G$16;$B$2:$B$16;B2;$A$2:$A$16;"<="&A2)
```

**Critérios de cálculo:**
- Considera os registros da mesma campanha.
- Soma os investimentos realizados até a data da linha analisada.
- Utiliza a função SOMASES para aplicar múltiplos critérios.

### Pacing Real

**Objetivo:** comparar o investimento acumulado com o orçamento previsto acumulado.

**Fórmula utilizada:**

```excel
=SEERRO(O2/F2;0)
```

**Interpretação:** demonstra o percentual do orçamento previsto que já foi consumido.

### Desvio de Pacing

**Objetivo:** identificar a diferença percentual entre o ritmo de investimento realizado e o planejado.

**Fórmula utilizada:**

```excel
=P2-1
```

**Interpretação:**
- Resultado negativo: investimento abaixo do ritmo planejado.
- Resultado igual a zero: investimento alinhado ao planejado.
- Resultado positivo: investimento acima do ritmo planejado.

## 4. Regras de alertas operacionais

**Objetivo:** classificar automaticamente a situação operacional da campanha considerando seu status e o percentual de Pacing Real.

**Fórmula utilizada:**

```excel
=SE(K2<>"Ativa";"Verificar status";SE(P2<0,9;"Abaixo do ritmo";SE(P2>1,1;"Acima do ritmo";"Dentro do ritmo")))
```

**Regras de classificação:**

| Condição | Classificação |
|---|---|
| Status diferente de Ativa | Verificar status |
| Pacing inferior a 90% | Abaixo do ritmo |
| Pacing entre 90% e 110%, inclusive | Dentro do ritmo |
| Pacing superior a 110% | Acima do ritmo |

A classificação é realizada automaticamente por meio de condições encadeadas utilizando a função SE.

## 5. Tecnologias e recursos utilizados

- Google Sheets: organização dos dados e aplicação de fórmulas.
- Google Looker Studio: visualização e acompanhamento dos indicadores.
- Funções utilizadas: SEERRO, SE e SOMASES.
- Recursos aplicados: cálculos condicionais, agregação por critérios, indicadores percentuais e regras de classificação operacional.

## 6. Contribuição para o negócio

A estrutura de indicadores permite:

- Acompanhar a eficiência das campanhas.
- Comparar custos de aquisição e geração de tráfego.
- Monitorar o consumo de orçamento.
- Identificar desvios em relação ao planejamento.
- Sinalizar situações que exigem investigação operacional.
- Apoiar análises gerenciais e decisões relacionadas à performance das campanhas.

## 7. Observações técnicas

- Os dados utilizados são fictícios e possuem finalidade demonstrativa.
- As fórmulas documentadas correspondem às utilizadas no Google Sheets.
- O intervalo de acumulação considera as linhas 2 a 16 da base original.
- Os alertas seguem os limites definidos na fórmula implementada.
- O documento descreve os cálculos efetivamente desenvolvidos no projeto.

---
## 8. Validação e Qualidade dos Indicadores

### Tratamento de cálculos

Foram aplicados controles nas fórmulas para reduzir inconsistências nos indicadores:

- **CTR e CPC:** utilização de SEERRO para evitar erros em operações com denominador igual a zero.
- **CPA:** retorno de valor vazio quando não existem conversões registradas.
- **Pacing Real:** tratamento de erros no cálculo da relação entre investimento acumulado e orçamento previsto acumulado.

### Regras de negócio

O acompanhamento operacional utiliza três faixas de classificação:

| Condição | Classificação |
|---|---|
| Pacing inferior a 90% | Abaixo do ritmo |
| Pacing entre 90% e 110% | Dentro do ritmo |
| Pacing superior a 110% | Acima do ritmo |

Campanhas com status diferente de "Ativa" recebem a classificação "Verificar status".

### Acumulação financeira

O investimento acumulado é calculado por campanha, considerando os registros até a data analisada.

Essa abordagem permite acompanhar a evolução dos gastos e comparar o investimento realizado com o orçamento previsto acumulado.

### Limitações do cenário demonstrativo

- Base de dados fictícia, utilizada para demonstração técnica.
- Indicadores calculados a partir dos registros disponíveis na planilha.
- Os resultados não representam dados reais de plataformas de mídia.
- A fórmula de investimento acumulado utiliza intervalos fixos até a linha 16, sendo necessário ampliar os intervalos caso novos registros sejam adicionados.


**Campaign Pulse | Digital Media Intelligence**

Projeto demonstrativo de Business Intelligence — 2026.
