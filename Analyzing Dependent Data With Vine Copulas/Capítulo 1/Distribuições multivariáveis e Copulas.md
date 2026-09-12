## Distribuições univariáveis
$X$: Variável aleatória
$x$: Valor observado
$F$: Função de distribuição
$f$: Função de densidade

A densidade de uma distribuição normal univariável com média $\mu\in\mathbb{R}$ e variância $\sigma^2>0$ é dada por:
$$
f(x;\ \mu,\ \sigma^2) = \frac{1}{\sqrt{2\pi\sigma^2}}\exp\{-\frac{1}{2}\frac{1}{\sigma^2}(x-\mu)^2\}
$$
A densidade para uma distribuição t Student, com média $\mu\in\mathbb{R}$, variância $\sigma^2>0$ e grau de liberdade $\nu>0$ é dada por:
$$
f_{\nu}(x;\ \mu, \ \sigma^2)\coloneqq \frac{\Gamma(\frac{\nu+1}{2})}{\Gamma(\frac{\nu}{2})\sqrt{(\pi\nu)}\sigma} \left\{ 1+\left(\frac{x-\mu}{\sigma}\right)^2 \frac{1}{\nu}\right\}^{-\frac{\nu+1}{2}}
 $$
 Para $\nu>2$, temos que para t Student:
 $$
E(X)=\mu
$$
$$
\text{Var}(X) = \frac{\nu}{\nu-2}\sigma^2
$$

Acontece que os parâmetros da distribuição das variáveis aleatórias geralmente são desconhecidos e devem ser estimados baseados em uma amostra identicamente e independentemente distribuída.

Usando o modelo paramétrico para $X$ com o vetor parâmetro $\theta$, é possível assumir que $X\sim f(\cdot;\theta)$.
O vetor parâmetro $\theta\in\Theta$ é estimado pela máxima verossimilhança:
$$
\hat{\theta}\coloneqq\underset{\theta\in\Theta}{\text{arg max}}
\prod^n_{i=1}f(x_i;\theta)$$

A função de distribuição $F(\cdot;\theta)$ é também estimada por $F(\cdot;\hat{\theta})$.
Caso não for assumido o modelo estatístico paramétrico, a distribuição empírica univariável é utilizada.
Considerando uma amostra i.i.d $x_1,\ldots,x_n$ de uma distribuição $F$, a função de distribuição empírica é definida por:
$$
\hat{F}(x) \coloneqq\frac{1}{n+1}\sum^n_{i=1}1_{x_i\leq x}\text{,  para todo }x
$$
Utiliza-se $n+1$ ao invés de $n$ para contornar problemas de contorno.

Para caracterizar a dependência entre diversas variáveis aleatórias, é necessário padronizar variáveis aleatórias. Para isso, é utilizado [[Probability Integral Transform (PIT)]].

## Distribuições Multivariáveis
Elas descreve o comportamento aleatório de diversas variáveis aleatórias.
Podemos distinguir as distribuições marginais, conjuntas e condicionais dentro das distribuições multivariadas.

### Distribuição Marginal
**Função de densidade**: $f_j(x_j)$,  $j=1,\ldots,d$
**Função de distribuição**: $F_j(x_j)$,  $j=1,\ldots,d$
### Distribuição conjunta
**Função de densidade**: $f(x_1,\ldots,x_d)$
**Função de distribuição**: $F(x_1,\ldots,x_d)$
### Distribuição condicional
**Função de densidade**: $f_{j|k}(x_j|x_k)$, $j\neq k$
**Função de distribuição**: $F_{j|k}(x_j|x_k)$, $j\neq k$


### Distribuição Elíptica
O vetor aleatório $X$ de dimensão $d$ possui uma distribuição elíptica somente se sua função de densidade possuir a representação:
$$
f(x; \ \mu,\Sigma) = k_d|\Sigma|^{-\frac{1}{2}}g((x-\mu)^\top\Sigma^{-1}(x-\mu) )
$$
onde $k_d\in\mathbb{R}$ é uma constante que depende da dimensão $d$, $\mu\in\mathbb{R}^d$ é um vetor média, $\Sigma\in\mathbb{R}^{d\times d}$ é uma matriz simétrica definida positiva e $g: \mathbb{R}^{+}_{0}\to\mathbb{R}^+_0$ é uma função independente da dimensão $d$. As distribuições multivariadas normais e t Students fazem parte dessa classe. $|\Sigma|$ representa o determinante da matriz $\Sigma$.

### Distribuição normal multivariada
Observamos a distribuição normal multivariada quando escolhemos
$$
g(t)\coloneqq\exp\left\{ -\frac{t}{2}\right\}
$$
e
$$
k_d=(2\pi)^{-\frac{d}{2}}
$$
Nesse caso dizemos que o vetor aleatório $X\coloneqq(X_1,\ldots,X_d)^\top$ é multivariado com distribuição normal, com vetor média $\mu\coloneqq(\mu_1,\ldots,\mu_d)^\top\in\mathbb{R}^d$ e matriz definida positiva de covariância $\Sigma=(\sigma_{ij})_{i,j=1,\ldots,d}\in\mathbb{R}^{d\times d}$ e podemos escrever que
$$
X\sim N_d(\mu, \ \Sigma)
$$
com
$$
E(X_i)=\mu_i
$$
$$
\text{Cov}(X_i,X_j)=\sigma_{ij}, \ \text{para todos } i,\ j = 1,\ldots,d 
$$
Além disso, as distribuições marginais satisfazem:
$$
X_i\sim N(\mu_i, \sigma_{ii}), \ \forall i =1,\ldots,d
$$
Finalmente, a densidade da distribuição normal multivariada é dada por:
$$
f_N(x;\ \mu,\Sigma) =  \frac{1}{(2\pi)^{d/2}}|\Sigma|^{-\frac{1}{2}}\exp\left\{-\frac{1}{2}(x-\mu)^\top\Sigma^{-1}(x-\mu) \right\}
$$

### Distribuições condicionais de distribuições normais multivariadas
É também de interesse as distribuições condicionais de sub-vetores de um vetor aleatório $X$ com distribuição normal. Considerando $X=(X_1,X_2)\in\mathbb{R}^{d_1+d_2}$, $\mu=(\mu_1^\top,\mu_2^\top)^\top\in\mathbb{R}^{d_1+d_2}$ para $d_1+d_2=d$ e partição
$$
\Sigma = 
\begin{pmatrix}
\Sigma_{11} & \Sigma_{12} \\
\Sigma_{12}^\top & \Sigma_{22}
\end{pmatrix}
$$
onde $\Sigma_{11}\in\mathbb{R}^{d_1\times d_1}$, $\Sigma_{22}\in\mathbb{R}^{d_2\times d_2}$ e $\Sigma_{12}\in\mathbb{R}^{d_1\times d_2}$.
Assim, a distribuição condicional de $X_2$ dado $X_1=x_1$ é
$$
X_2|X_1=x_1 \sim N_d(\mu_{2|1}, \ \Sigma_{2|1})
$$
onde o vetor de média condicional é determinado por
$$
\mu_{2|1} \coloneqq \mu_2+\Sigma_{12}^\top\Sigma_{11}^{-1}(x_1-\mu_1)
$$
e a matriz de covariância condicional é determinada por:
$$
\Sigma_{2|1} \coloneqq\Sigma_{22}-\Sigma_{12}^\top\Sigma_{11}^{-1}\Sigma_{12}
$$

### Distribuição t-Student multivariada
É dito que um vetor aleatório $X=(X_1,\ldots,X_d)^\top$ possui uma distribuição multivariada t-Student $t_d(\nu,\mu,\Sigma)$ com $\nu>0$ graus de liberdade, vetor média $\mu\in\mathbb{R}^d$ e uma matriz parâmetro de escala $\Sigma$, se sua densidade for dada por:
$$
f_t(x; \ \nu; \ \mu, \Sigma)=\frac{\Gamma(\frac{\nu+d}{2})}{\Gamma(\frac{\nu}{2})(\pi\nu)^{d/2}}|\Sigma|^{-1/2} \left\{ 1+\frac{1}{\nu}(x-\mu)^\top \Sigma^{-1} (x-\mu) \right\}^{-\frac{\nu+d}{2}}
$$
Importante notar que para $\nu>2$ a matriz de variância covariância de $X$ é dada por $\frac{\nu}{\nu-2}\Sigma$, pois $\Sigma$ não representa a matriz real de covariância, e sim apenas uma matriz de escala.

A distribuição multivariada de t-Student também permite a representação estocástica:

Se  $X=(X_1,\ldots,X_d)^\top \sim t_d(\nu,\mu,\Sigma)$ com $\nu>2$ e se $Y=(Y_1,\ldots,Y_d)^\top \sim N_d(0,\text{Cov})$ com a matriz de covariância $\text{Cov}=(\text{cov}_{ij})_{i,j=1\ldots,d}$ onde
$$
\text{cov}_{ij}=\cases{\sigma^2 \ \ \ \ \ \ \ \ \text{se }i=j \\ \sigma^2\rho_{ij} \ \ \   \text{se }i\neq j}
$$
e $\nu S^2/\sigma^2\sim \chi^2_\nu$  com o g.l $\nu$ independente de $Y$, então a identidade
$$
X\overset{\mathcal{D}}{=}S^{-1}Y+\mu
$$
é verdadeira.
Dessa identidade, podemos tirar que a distribuição condicional de $X$ dado $S^2=s^2$ é:
$$
X|S^2=s^2\sim N_d\left(\mu,\frac{1}{s^2}\text{Cov}\right)
$$
Escolhendo então
$$
k_d\coloneqq\frac{\Gamma(\frac{\nu+d}{2})}{\Gamma(\frac{\nu}{2})}
$$
e
$$
g(t)=\left(1+\frac{t}{\nu}  \right)^{-(\nu+d)/2}
$$
e usando a equação
$$
f_t(x; \ \nu; \ \mu, \Sigma)=\frac{\Gamma(\frac{\nu+d}{2})}{\Gamma(\frac{\nu}{2})(\pi\nu)^{d/2}}|\Sigma|^{-1/2} \left\{ 1+\frac{1}{\nu}(x-\mu)^\top \Sigma^{-1} (x-\mu) \right\}^{-\frac{\nu+d}{2}}
$$
chegamos que a distribuição multivariável t-Student é membro das distribuições elípticas.

### Distribuição standard t Student bivariada
É um caso especial com $d=2$, vetor média $\mu$ nulo e matriz parâmetro de escala:
$$
\Sigma_p = \begin{pmatrix}
1 & \rho \\
\rho & 1
\end{pmatrix}
$$

Sua função de densidade é dada por:
$$
f_t(x_1,x_2; \ \nu , \rho)=\frac{\Gamma(\frac{\nu+2}{2})(1-\rho^2)^{-1/2}}{\Gamma(\frac{\nu}{2})(\pi\nu)} \left\{ 1+\frac{1}{\nu}\frac{x_1^2-2x_1x_2\rho+x_2^2}{1-\rho^2} \right\}^{-\frac{\nu+2}{2}}
$$

### Distribuições condicionais de t multivariada
Considerando o vetor aleatório  $X=(X_1,\ldots,X_d)^\top \sim t_d(\nu,0,\Sigma)$ com a partição de $\Sigma$ para $X=(X_1,X_2)^\top$ sendo ainda
$$
\Sigma = 
\begin{pmatrix}
\Sigma_{11} & \Sigma_{12} \\
\Sigma_{12}^\top & \Sigma_{22}
\end{pmatrix}
$$
temos que a densidade condicional de $X_2$ dado $X_1$ é dada por:
$$
f_{X_2|X_1}(x_2|x_1)=\frac{\Gamma(\frac{\nu+d}{2})}{\Gamma(\frac{\nu+d_1}{2})(\pi\nu)^{d_1/2}}\frac{|\Sigma_{11}|^{1/2}}{|\Sigma|^{1/2}} \frac{[1+(1/\nu)x_1^\top\Sigma_{11}^{-1}x_1]^{\frac{\nu+d_1}{2}}}{[1+(1/\nu)x^\top\Sigma x]^{\frac{\nu+d}{2}}}
$$
Generalizando, temos que se $X=(X_1,\ldots,X_d)^\top \sim t_d(\nu,\mu,\Sigma)$, a distribuição condicional de $X_2$ dado $X_1=x_1$ segue $t_{d_2}(\nu_{2|1},\mu_{2|1},\Sigma_{2|1})$, sendo:
$$
\mu_{2|1}\coloneqq\mu_2+\Sigma_{12}^\top\Sigma_{11}^{-1}(x_1-\mu_1)
$$
$$
\Sigma_{2|1}\coloneqq\frac{\nu+(x_1-\mu_1)^\top\Sigma_{11}^{-1}(x_1-\mu_1)}{\nu+d_1}(\Sigma_{22}-\Sigma_{12}^\top\Sigma_{11}^{-1}\Sigma_{12})
$$
$$
\nu_{2|1}=\nu+d_1
$$
## Características de dados multivariados
As distribuições paramétricas, como a normal multivariada e a t student, não conseguem acomodar diferentes tipos de distribuições marginais, já que todas elas devem possuir a mesma distribuição. Por isso, essas distribuições paramétricas são chamadas de distribuições simétricas.

A não simetria observada entre pares de variáveis aleatórias pode ser a indicação de dependência de caudas pesadas entre esses pares, ou seja, essas duas variáveis assumem valores muito altos ou muito baixos. A distribuição normal multivariada não possui esse tipo de dependência, enquanto a t student multivariada possui um parâmetro para controlar essa dependência.

Importante notar que apesar da t student multivariada possuir um parâmetro que controla a dependência de cauda, ela ainda continua sendo simétrica, pois ambos extremos ainda são previstos com a mesma probabilidade.


## Conceito de uma Copula e Teorema de Sklar
A utilização de copula em dados multivariados permite o modelamento individual das distribuições marginais. Primeiramente, nota-se que o formato dos scatter plots entre as duas variáveis depende da escala delas, então e necessária a normalização de cada uma delas. Para isso,  a probability integral transform será utilizada. 

Assim, queremos caracterizar a dependência entre variáveis aleatórias com uma mesma distribuição marginal, a distribuição uniforme. Desse modo, separamos a dependência entre os componentes e as distribuições marginais.

Uma cópula $C$ de $d$ dimensões é uma função de distribuição multivariada em um hipercubo de $d$ dimensões $[0,1]^d$ com distribuições marginais uniformes.

A densidade da cópula é denotada por $c$ e é obtida através da derivação parcial de $C$
$$
c(u_1,\ldots,u_D) :=\frac{\partial^d}{\partial u_1\ldots\partial u_d}C(u_1\ldots u_d)
$$
para todos $u$ em $[0,1]^d$.

### Teorema de Sklar
Seja $X$ um vetor aleatório de dimensão $d$, com função distribuição conjunta $F$ e funções de distribuição marginal $F_i$ com $i=1,\ldots,d$. A distribuição conjunta pode ser expressada por
$$
F(x_1,\ldots,x_d) = C(F_1(x_1),\ldots,F_d(x_d))
$$
com função de densidade 
$$
f(x_1,\ldots,x_d) = c(F_1(x_1),\ldots,F_d(x_d))f_1(x_1)\ldots f_d(x_d)
$$
para uma copula $C$ de $d$ dimensões, com uma densidade de copula $c$.

Para distribuições continuas, a cópula $C$ é única.

Podemos analisar também o contrário. A copula correspondente a distribuição multivariada $F$ com funções de distribuição marginal $F_i$ com $i=1,\ldots,d$ é
$$
C(u_1,\ldots,u_d) = F(F_1(u_1)^{-1},\ldots,F_d(u_d)^{-1})
$$
e sua densidade de copula é determinada por
$$
c(u_1,\ldots,u_d)=\frac{f(F_1(u_1)^{-1},\ldots,F_d(u_d)^{-1})}{f_1(F_1(u_1)^{-1})\ldots f_d(F_d(u_d)^{-1})}
$$

Existem duas grandes aplicações para o Teorema de Sklar.
- Estimação da dependência entre duas variáveis normalizadas
Essa dependência pode ser caracterizada por uma copula, considerando uma amostra independente $x_i=(x_{i1},\ldots, x_{id})^\top$, com $i=1,\ldots,n$. Para isso, é construída uma pseudo-copula usando uma PIT estimada com
$$
u_{ij} \coloneqq F_j(x_{ij};\hat{\theta_j})
$$
para $j=1,\ldots,d$ e $i,\ldots,n$. $\hat{\theta_j}$ é a estimação do parâmetro $\theta_j$ em um modelo estatístico paramétrico para a j-ésima marginal. A dependência $U_{ij}$ pode ser utilizada para encontrar um modelo apropriado para a cópula.
- Construção de distribuições multivariadas
O teorema nos permite utilizar marginais arbitrárias, com cópulas ou densidade de cópulas, para construir uma nova distribuição multivariada.

### Aproximação empírica de cópula
Para o caso de uma cópula bivariada
$$
\hat{C}(u_1,u_2) \coloneqq \frac{1}{n+1}\sum^n_{i=1}1_{\{u_{1i}\leq u_1,u_{2i}\leq u_2\}}
$$
para todos $0\leq u_1,u_2\leq1$.