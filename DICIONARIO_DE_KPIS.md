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

**Interpretação:** demonstra o percentual do orçamento previsto acumulado que já foi consumido.

**Observação:** quando ocorre erro no cálculo, a fórmula retorna zero por meio da função SEERRO. Esse resultado deve ser interpretado considerando os valores utilizados no cálculo.

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
=SE(K2<>"Ativa";"Ver
