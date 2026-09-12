Podemos caracterizar copulas como funções que juntam funções de distribuição multivariadas com suas funções marginais unidimensionais. Podemos também caracteriza-las como funções de distribuição cujas distribuições marginais unidimensionais são uniformes. Mas precisamos definir precisamente o que copulas são.

Precisamos imaginar um par de variáveis aleatórias $X$ e $Y$, suas funções de distribuição $F(x)=P[X\leq x]$ e $G(y)=[Y\leq y]$ e finalmente a função de distribuição conjunta $H(x,y)=[X\leq x,Y\leq y]$. Para cada par de números reais $(x,y)$ obtemos 3 valores associados: $F(x)$, $G(y)$ e $H(x,y)$, todos dentro do intervalo $[0,1]$. Essa correspondência que designa um valor para cada par de valores das distribuições individuais também e uma função. Essa função é uma copula.

Para chegarmos na definição acima, é será necessário definir a noção de não-decrescente de funções univariadas para funções multivariadas.

## Preliminares
Primeiramente, vamos considerar o caso bidimensional e desenvolver a noção de uma função "2-increasing", ou seja, uma analogia bidimensional à função não decrescente unidimensional. Seja $\mathbb{R}$ ser a reta dos reais $(-\infty,\infty)$, $\overline{\mathbb{R}}$ a reta real extendida $[-\infty,\infty]$ e $\overline{\mathbb{R}^2}$ o plano real $\overline{\mathbb{R}}\times\overline{\mathbb{R}}$.

Um retângulo em $\overline{\mathbb{R}^2}$ é o produto cartesiano $B$ de dois intervalos fechados
$$
B = [x_1,x_2]\times[y_1,y_2]
$$
Os vértices do retângulo $B$ são os pontos $(x_1,y_1)$,  $(x_1,y_2)$,  $(x_2,y_1)$,  $(x_2,y_2)$.
O quadrado unitário é representado por $I^2$, onde $I=[0,1]$.

Uma função real de duas variáveis $H$ é uma função cujo domínio $DomH$ é subconjunto de $\overline{\mathbb{R}^2}$ e seu contradomínio é subconjunto de $\mathbb{R}$.

### **Definição 2.1.1**
Seja $S_1$ e $S_2$ subconjuntos não-vazios de $\overline{\mathbb{R}}$ e seja $H$ uma função real de duas variáveis com domínio $DomH=S_1\times S_2$. Seja $B = [x_1,x_2]\times[y_1,y_2]$ um retângulo com todos os vértices em $DomH$. O $H$-volume (probabilidade de estar dentro do retângulo) de $B$ é dado por
$$
V_H(B) = H(x_1,y_1)-H(x_2,y_1)-H(x_1,y_2)+H(x_2,y_2)
$$
Se definirmos as diferenças de primeira ordem de $H$ no retângulo $B$ como
$$
\Delta^{y_2}_{y_1}H(x,y)=H(x_2,y)-H(x_1,y)
$$
e
$$
\Delta^{y_2}_{y_1}H(x,y)=H(x,y_2)-H(x,y_1)
$$
então o $H$-volume do retângulo $B$ é a diferença de segunda ordem de $H$ em $B$
$$
V_H(B)=\Delta^{y_2}_{y_1}\Delta^{y_2}_{y_1}H(x,y)
$$
### **Definição 2.1.2**
Uma função real H de duas variáveis é 2-crescente se $V_H(B)\geq0$ para todos retângulos $B$ com vértices em $DomH$. 
É importante notar que a função ser 2-crescente não implica que ela seja não-decrescente para cada um de seus argumentos. Ela pode ser decrescente para $x$ e mesmo assim ser 2-crescente. Ou seja, as derivadas parciais podem ser negativas, porem a derivada mista deve ser positiva.

### **Lema 2.1.3**
Seja $S_1$ e $S_2$ subconjuntos não-vazios de $\overline{\mathbb{R}}$ e seja $H$ uma função real de duas variáveis com domínio $DomH=S_1\times S_2$. Seja $x_1$, $x_2$ pertencentes de $S_1$ com $x_1\leq x_2$ e seja $y_1$, $y_2$ pertencentes de $S_2$ com $y_1\leq y_2$. Então, a função $t\mapsto H(t,y_2)-H(t,y_1)$ é não-decrescente em $S_1$ e a função $t\mapsto H(x_1,t)-H(x_2,t)$ é não-decrescente em $S_2$.

Com esse lema e a aplicação de uma próxima hipótese, podemos mostrar que uma função 2-crescente é não decrecente em cada argumento.

Suponha que $S_1$ tenha um menor elemento $a_1$ e que $S_2$ possua um menor elemento $a_2$. Dizemos que a função $H$ de $S_1\times S_2$ em $\mathbb{R}$ é aterrada se $H(x,a_2)=H(a_1,y)=0$ para todos $(x,y)$ em $S_1\times S_2$.

Com isso, temos:
### **Lema 2.1.4**
Seja $S_1$ e $S_2$ subconjuntos não-vazios de $\overline{\mathbb{R}}$ e seja $H$ uma função aterrada de duas variáveis com domínio $DomH=S_1\times S_2$. Então, $H$ é não-decrescente em cada um de seus argumentos.
**Prova**:
Como a função é 2-crescente temos:
$$
 V_H(B) = H(x_1,y_1)-H(x_2,y_1)-H(x_1,y_2)+H(x_2,y_2) \geq 0 \Rightarrow 
$$
$$
H(x_1,y_1)-H(x_2,y_1)\geq H(x_1,y_2)-H(x_2,y_2)
$$
Seja $a_1$ o menor elemento de $S_1$. Então, como $H$ é aterrada:
$$
H(a_1,y_1)-H(x_2,y_1)\geq H(a_1,y_2)-H(x_2,y_2) \Rightarrow
$$
$$
0-H(x_2,y_1)\geq0-H(x_2,y_2) \Rightarrow H(x_2,y_2) -H(x_2,y_1)\geq 0
$$
Isso prova que ela é não-decrescente no argumento $y$ (na vertical). Para provar que ela é não decrescente para o argumento $x$ é análogo.

Agora, vamos supor que $S_1$ possui um maior elemento $b_1$ e $S_2$ possui um maior elemento $b_2$. Dizemos que a função $H$ possui margens e que elas são as funções $F$ e $G$ dadas por:
$$
DomF = S_1, \ \ F(x)=H(x,b_2)
$$
$$
DomG = S_2, \ \ F(y)=H(b_1,y)
$$
Agora, a respeito das funções 2-crescentes aterradas e com margem, temos o último lema da seção
### **Lema 2.1.5**
Seja $S_1$ e $S_2$ subconjuntos não-vazios de $\overline{\mathbb{R}}$ e seja $H$ uma função aterrada, com margens e de duas variáveis com domínio $DomH=S_1\times S_2$. Sejam $(x_1,y_1)$ e $(x_2,y_2)$ quaisquer pontos em $S_1\times S_2$. Então:
$$
|H(x_2,y_2)-H(x_1,y_1)|\leq |F(x_2)-F(x_1)|+|G(y_2)-G(y_1)| 
$$

## Copulas
Podemos agora finalmente definir formalmente as funções copulas.
Primeiro, definimos subcopulas como uma classe de funções aterradas, com margens e 2-crescentes. Depois, definimos copulas como subcopulas com domínio $I^2$.

### Definição 2.2.1
Uma subcopula de 2 dimensões é uma função $C'$ com as seguintes propriedades:
1. $DomC'$=$S_1\times S_2$, onde $S_1$ e $S_2$ são subconjuntos de $I$ contendo $0$ e $1$;
2. $C'$ é aterrada e 2-crescente;
3. Para cada $u$ em $S_1$ e $v$ em $S_2$, temos
$$
C'(u,1)=u \ \ \text{e} \ \ C'(1,v) = v
$$
Importante notar que para cada $(u,v)$ em $DomC'$, $0\leq C'\leq1$, então $CDomC'$ também é subconjunto de $I$.

### Definição 2.2.2
Uma copula de 2 dimensões é uma 2-subcopula C com domínio $I^2$.
A copula é uma fução $C$ de $I^2$ para $I$ com as propriedades:
1. Para todo $u,v$ em $I$:
$$
C(u,0)=C(0,v)=0
$$
e
$$
C(u,1)=u \ \ \text{e} \ \ C(1,v) = v
$$
2. Para todos $u_1,u_2,v_1,v_2$ em $I$, de modo que $u_1\leq u_2$  e $v_1\leq v_2$:
$$
C(u_2,v_2)-C(u_2,v_1)-C(u_1,v_2)+C(u_1,v_1)\geq0
$$
Por conta da copula ser definida por $C(u,v)=V_C([0,u]\times[0,v])$, podemos entender ela como a atribuição de um número em $I$ para o retângulo $[0,u]\times[0,v]$.


### Teorema 2.2.3
Seja $C'$ uma subcopula. Então, para cada $(u,v)$ no $DomC'$:
$$
\max(u+v-1,0)\leq C'(u,v)\leq \min(u,v)
$$
**Prova**:
Sabemos que a subcopula é menor igual a seus valores marginais:
$$
C'(u,v)\leq C'(u,1) \Rightarrow C'(u,v)\leq u
$$
$$
C'(u,v)\leq C'(1,v) \Rightarrow C'(u,v)\leq v
$$
Então:
$$
C'(u,v)\leq \min(u,v)
$$
Agora, sabemos que $V_{C'}([u,1]\times[v,1])\geq0$. Disso podemo tirar:
$$
C'(u,v)-C'(u,1)-C'(1,v)+C'(1,1)\geq0 \Rightarrow C'(u,v)\geq u+v-1
$$
Enfim, temos:
$$
\max(u+v-1,0)\leq C'(u,v)\leq \min(u,v) \ \ \square
$$

Como toda copula é uma subcopula, a desigualdade acima vale para elas também. Importante dizer que os extremos da desigualdade também são cópulas, denotadas por $M(u,v)=\min(u,v)$ (Fréchet-Hoeffding upper bound) e $W(u,v)=\max(u+v-1,0)$ (Fréchet-Hoeffding lower bound).
Desse modo, para toda copula $C$ temos
$$
W(u,v)\leq C(u,v)\leq M(u,v)
$$

Além das copulas $W(u,v)$ e $M(u,v)$, temos também a copula $\Pi(u,v)=uv$ (copula produto).

### Teorema 2.2.4
Seja $C'$ uma subcopula. Para todos $(u_1,u_2)$, $(v_1,v_2)$ no $DomC'$, vale:
$$
|C'(u_2,v_2)-C'(u_1,v_1)| \leq |u_2-u_1|+|v_2-v_1|
$$
Então, $C'$ é uniformemente contínua em seu domínio (condição de Lipschitz).

### Definição 2.2.5
Seja $C$ uma copula e $a$ um número real em $I$. A Seção horizontal de $C$ em $a$ é a função de $I$ em $I$ dada por $t\mapsto C(t,a)$. A Seção vertical de $C$ em $a$ é a função de $I$ em $I$ dada por $t\mapsto C(a,t)$. Por fim, a seção diagonal de $C$ é a função $\delta_C$ de $I$ em $I$ definida por $\delta_C(t)=C(t,t)$.

Como consequência do lema 2.1.4 e do teorema 2.2.4, temos:
### Corolário 2.2.6
As seções horizontais, verticais e diagonais de uma copula $C$ são todas não-decrescentes e uniformemente contínuas em $I$.

### Teorema 2.2.7
A respeito das derivadas parciais de uma copula, para qualquer $v$ em $I$, $\frac{\partial}{\partial u}C(u,v)$ existe para quase todo $u$. Para tais $u$ e $v$, temos:
$$
0\leq\frac{\partial}{\partial u}C(u,v)\leq1
$$
O mesmo vale para a parcial de $v$. Para ela temos:
$$
0\leq\frac{\partial}{\partial v}C(u,v)\leq1
$$

### Teorema 2.2.8
Seja $C$ uma copula. Se $\frac{\partial}{\partial v}C(u,v)$ e $\frac{\partial^2}{\partial u \partial v}C(u,v)$ são contínuas em $I^2$ e  $\frac{\partial}{\partial u}C(u,v)$ existe para todo $u \in (1,0)$ quando $v=0$, então  $\frac{\partial}{\partial u}C(u,v)$ e $\frac{\partial^2}{\partial u \partial v}C(u,v)$ existem em $(0,1)^2$ e $\frac{\partial^2}{\partial u \partial v}C(u,v)=\frac{\partial^2}{\partial u \partial v}C(u,v)$.


## Teorema de Sklar
Este teorema elucida o papel das copulas na relação entre funções de distribuição e suas funções marginais univariadas. 

### Definição 2.3.1
A função de distribuição é uma função $F$ com domínio $\overline{\mathbb{R}}$ tal que
- $F$ é não-decrescente
- $F(-\infty)=0$ e $F(\infty)=1$

### Definição 2.3.2
A função de distribuição conjunta é a função $H$ de domínio $\overline{\mathbb{R}}^2$ tal que
- $H$ é 2-crescente
- $H(x,-\infty)=H(-\infty,y)=0$ e $H(\infty,\infty)=1$
Assim, $H$ é aterrada e possui margens dadas por $F(x)=H(x,\infty)$ e $G(y)=H(\infty,y)$. Podemos notar que $F$ e $G$ também são funções de distribuição.

### Teorema 2.3.3 (Teorema de Sklar)
Seja $H$ uma função de distribuição conjunta com margens $F$ e $G$. Existe uma copula $C$, tal que para qualquer $x$ e $y$ na reta real, vale:
$$
H(x,y) = C(F(x),G(y))
$$
Se $F$ e $G$ forem continuas, $C$ é única. Caso contrário, $C$ é determinada unicamente em $\text{Im} F \times \text{Im} G$.

### Lema 2.3.4
Seja $H$ uma função de distribuição conjunta com margens $F$ e $G$. Existe uma única subcopula cuja
- $\text{Dom}C'= \text{Im}F\times\text{Im}G$
- Para todos $x$ e $y$ na reta real, $H(x,y) = C'(F(x),G(y))$

### Lema 2.3.5
Seja $C'$ uma subcopula. Existe uma copula $C$ tal que $C(u,v)=C'(u,v)$ para todos $(u,v)$ em Dom$C'$. Em outras palavras, qualquer subcopula pode ser extendida a uma copula. 

### Definição 2.3.6
Seja $F$ uma função de distribuição. A quase-inversa de $F$ é qualquer função $F^{(-1)}$ com domínio $I$ tal que
1) Se $t$ está em Ran$F$, então $F^{(-1)}(t)$ é qualquer número $x$ na reta real tal que $F(x)=t$ para todo $t$ em Ran$F$.
2) Se $t$ não está em Ran$F$, então $F^{(-1)}(t) = \inf\{x|F(x)\geq t \}=\sup\{x|F(x)\leq t \}$ 
