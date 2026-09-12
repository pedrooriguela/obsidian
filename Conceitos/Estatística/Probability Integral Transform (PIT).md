---
tags:
  - probabilidade
  - estatistica
  - simulacao
aliases:
  - Probability Integral Transform
  - Transformada Integral da Probabilidade
  - PIT
---
# Glossário: Probability Integral Transform (PIT)

## 1. O que é?
A **Probability Integral Transform** (Transformada Integral da Probabilidade) é um teorema fundamental da teoria das probabilidades que estabelece uma relação direta e bijejetiva entre qualquer variável aleatória contínua e a distribuição Uniforme Padrão $U \sim \text{Uniforme}(0, 1)$.

### O Teorema Directo
Seja $X$ uma variável aleatória contínua com Função de Distribuição Acumulada (CDF) dada por $F_X(x) = P(X \le x)$, assumida aqui como estritamente crescente e contínua. Se aplicarmos a própria função $F_X$ sobre a variável aleatória $X$, a nova variável gerada, $U$, será uniformemente distribuída entre 0 e 1:

$$U = F_X(X) \implies U \sim \text{Uniforme}(0, 1)$$

**Demonstração Rápida:**
A CDF de $U$ para qualquer $u \in (0, 1)$ é calculada como:
$$F_U(u) = P(U \le u) = P(F_X(X) \le u) = P(X \le F_X^{-1}(u)) = F_X(F_X^{-1}(u)) = u$$
Como $F_U(u) = u$, esta é, por definição, a CDF de uma $\text{Uniforme}(0, 1)$.

---

## 2. O Teorema Inverso (Amostragem por Transformação Inversa)
O princípio também funciona na direção oposta. Se tivermos uma variável uniforme $U \sim \text{Uniforme}(0, 1)$ e a injetarmos na função inversa da CDF (também chamada de *função quantil*) de uma distribuição desejada, o resultado será uma variável que segue exatamente essa distribuição alvo:

$$X = F_X^{-1}(U) \implies X \sim F_X$$

> [!tip] **Intuição Geométrica**
> A CDF $F_X(x)$ mapeia os valores do eixo $X$ (que podem ir de $-\infty$ a $+\infty$) para o eixo $Y$ de probabilidades (que está estritamente contido entre $0$ e $1$). O PIT afirma que o preenchimento desse eixo $Y$ ocorre de forma perfeitamente homogênea (uniforme).

---

## 3. Para que é usada? (Aplicações Principais)

### A. Geração de Números Aleatórios (Simulação de Monte Carlo)
Computadores são excelentes para gerar números pseudo-aleatórios uniformes entre 0 e 1, mas não sabem nativamente como gerar dados de distribuições complexas (como uma distribuição Weibull, Exponencial ou Normal). 
* **Uso:** Utiliza-se o teorema inverso. O computador gera $u \sim \text{Uniforme}(0, 1)$ e calcula-se $x = F_X^{-1}(u)$ para simular observações de $X$.

### B. Testes de Aderência e Avaliação de Modelos (*Goodness-of-Fit*)
Se você ajustou um modelo preditivo ou uma distribuição teórica a um conjunto de dados empíricos, você quer saber se o modelo é válido.
* **Uso:** Aplica-se a CDF estimada do modelo $\hat{F}$ sobre os dados reais observados $x_1, x_2, \dots, x_n$. Se o modelo estiver correto, os valores transformados $u_i = \hat{F}(x_i)$ devem se comportar como uma amostra uniforme em $(0,1)$. Isso pode ser verificado visualmente (via histograma ou gráfico QQ) ou formalmente (via teste de Kolmogorov-Smirnov). Em modelos de previsão de séries temporais (como GARCH), resíduos transformados via PIT são usados para validar a calibrada da densidade de previsão.

### C. Teoria de Cópulas
Em finanças e análise de risco multidimensional, modelar a dependência conjunta de variáveis com distribuições marginais diferentes (ex: modelar a perda de ações e o risco de crédito juntos) é complexo.
* **Uso:** O PIT é usado para "padronizar" todas as variáveis marginais, transformando-as individualmente em distribuições $\text{Uniforme}(0,1)$ através de suas respectivas CDFs. Uma vez uniformizadas, a estrutura de dependência pura entre elas pode ser isolada e modelada utilizando uma **Cópula**, sem a interferência das escalas originais das variáveis.