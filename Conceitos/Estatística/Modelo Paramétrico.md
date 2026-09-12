---
tags:
  - estatistica
  - inferencia
  - modelagem
aliases:
  - Modelo Paramétrico
  - Vetor Parâmetro
  - Estimação Paramétrica
---

# Glossário: Modelagem e Estimação Paramétrica

## 1. Modelo Paramétrico
Um **modelo paramétrico** é uma coleção de distribuições de probabilidade indexada por um conjunto de parâmetros de dimensão fixa e finita. Ele assume que a forma matemática da densidade dos dados é conhecida, restringindo o problema a um espaço controlado.

* **Definição Formal:** É a família de funções de densidade (FDP) ou de massa (FMP) dada por:
  $$\mathcal{P} = \{ f(x; \theta) : \theta \in \Theta \}$$
  Onde $\mathcal{X}$ é o espaço amostral e $\Theta \subseteq \mathbb{R}^k$ (com $k < \infty$) é o espaço paramétrico.
* **Propriedade Fundamental (Identificabilidade):** O modelo deve ser injetivo. Ou seja, dois parâmetros distintos não podem gerar a mesma distribuição:
  $$\text{Se } \theta_1 \neq \theta_2 \implies f(x; \theta_1) \neq f(x; \theta_2) \quad \text{para algum } x \in \mathcal{X}$$

---

## 2. Vetor Parâmetro ($\theta$)
O **vetor parâmetro** $\theta = (\theta_1, \theta_2, \dots, \theta_k)^T \in \mathbb{R}^k$ é o conjunto finito de constantes que governa o comportamento geométrico, analítico e os momentos (média, variância, etc.) de uma distribuição dentro do modelo $\mathcal{P}$.

* **Espaço Paramétrico ($\Theta$):** O domínio geométrico que delimita os valores matematicamente válidos para $\theta$.
* **Geometria da Informação:** Em termos avançados, $\Theta$ funciona como uma variedade Riemanniana curva, onde as distâncias locais são medidas pela **Matriz de Informação de Fisher** $I(\theta)$:
  $$I_{ij}(\theta) = E_\theta \left[ \frac{\partial}{\partial \theta_i} \ln f(X; \theta) \cdot \frac{\partial}{\partial \theta_j} \ln f(X; \theta) \right]$$

---

## 3. Estimação Paramétrica
É o procedimento inferencial que utiliza dados observados de uma amostra aleatória i.i.d. $\mathbf{X} = (X_1, \dots, X_n)$ para aproximar o "parâmetro verdadeiro" e oculto $\theta_0 \in \Theta$ que gerou os dados.

> [!important] **Distinção Crucial: Estimador vs. Estimativa**
> * **Estimador ($\hat{\theta}$):** É uma função matemática da amostra ($\hat{\theta} = g(X_1, \dots, X_n)$). Por depender de variáveis aleatórias, o estimador é uma **variável aleatória** com distribuição própria.
> * **Estimativa ($\hat{\theta}_{obs}$):** É o **valor numérico estático** obtido quando os dados reais observados são aplicados ao estimador ($\hat{\theta}_{obs} = g(x_1, \dots, x_n)$).

### Principais Métodos de Estimação

#### A. MÁXIMA VEROSSIMILHANÇA (MLE)
Busca o vetor $\theta$ que maximiza a probabilidade conjunta de observar a amostra obtida. Baseia-se na maximização da log-verossimilhança $\ell(\theta)$:

$$\ell(\theta; \mathbf{x}) = \sum_{i=1}^n \ln f(x_i; \theta)$$

O estimador $\hat{\theta}_{MLE}$ é o ponto crítico encontrado ao igualar a **Função de Score** a zero:

$$U(\theta) = \nabla_\theta \ell(\theta; \mathbf{x}) = \mathbf{0}$$

* *Propriedade:* É assintoticamente eficiente, atingindo o **Limite de Variância Mínima de Cramér-Rao** ($\text{Var}(\hat{\theta}) \ge \frac{1}{n} I(\theta_0)^{-1}$) quando $n \to \infty$.

#### B. MÉTODO DOS MOMENTOS (MoM)
Consiste em construir um sistema de equações que iguala os momentos teóricos da população (que dependem de $\theta$) aos momentos empíricos calculados diretamente da amostra:

$$\mu_k(\theta) = E[X^k] \quad \Longleftrightarrow \quad m_k = \frac{1}{n} \sum_{i=1}^n X_i^k$$

* *Propriedade:* Costuma ser computacionalmente mais simples que o MLE, mas geralmente apresenta maior variância em amostras finitas.