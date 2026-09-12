# Exercício 2.1
## Verificando o exemplo 2.1
Seja $H(x,y)=\max(x,y)$. Para qualquer $y$ e $x_2\gt x_1$, existem dois casos. Se
$$
\max(x_2,y) = y
$$
então $y$ também é maior que $x_1$. A desigualdade ficaria:
$$
H(x_2,y_0)-H(x_1,y_0)\geq 0 \Rightarrow y-y\ge0
$$
o que é verdade.
Agora caso $x_2\gt y$, temos que o resultado para $\max(x_1,y)$ é $x_1$ ou $y$. Para os dois casos temos:

$$
H(x_2,y_0)-H(x_1,y_0)\geq 0 \Rightarrow x_2-x_1\ge0 \ \ \ \square
$$
$$
H(x_2,y_0)-H(x_1,y_0)\geq 0 \Rightarrow x_2-y\ge0 \ \ \ \square
$$
Para $y_1$ e $y_2$ a situação é análoga. Logo, $H(x,y)=\max(x,y)$ é não decrescente.

Agora, analisando se ela é 2-crescente, precisamos verificar se:
$$
V_H(B)\geq0
$$
sendo $B$ o quadrado unitário.
Sendo $y_2\gt y_1$ e $x_2 \gt x_1$, observamos:
$$
\max(x_2,y_2)-\max(x_2,y_1)-\max(x_1,y_2)+max(x_1,y_1)\ge 0
$$
Basta demonstrar um caso de valores para nossas variáveis em que a função de massa seja menor que 0 para provarmos que a função não é 2-crescente. Sendo $x_2=y_2=1$ e $x_1=y_1=0$ temos:
$$
1-1-1-0\ge0 \Rightarrow -1\ge0
$$
Logo, a função não é 2-crescente.
## Verificando o exemplo 2.2
Seja $H(x,y)=(2x-1)(2y-1)$ definida no quadrado unitário $I^2$.
Temos
$$
4xy-2x+2y+1=0
$$
Deixando $x$ em evidência:
$$
(4y-2)x +2y+1=0
$$
Vemos que a função é decrescente para $x$ quando
$$
4y-2\lt0
$$
Logo, temos que $x$ é decrescente para todo $y\in(0,1/2)$. O mesmo vale para $y$. Assim, vemos que $H$ é decrescente para ambos de seus argumentos.
Porém podemos verificar que:
$$
V_H(I^2)=(2x_2-1)(2y_2-1)-(2x_2-1)(2y_1-1)-(2x_1-1)(2y_2-1)+(2x_1-1)(2y_1-1)\ge0
$$
A expressão pode ser simplificada para
$$
2(y_2-y_1)(x_2-x_1)\ge0
$$
O que é verídico. Assim, verificamos que H é 2-crescente porém decrescente em seus argumentos.

# Exercício 2.2
- $M(u,v)=min(u,v)$
Para verificarmos que $M(u,v)$ é uma copula, precisamos mostrar que ela é uma função aterrada, 2-crescente e com margem dentro do quadrado unitário $I^2$.
É fácil notar que é uma função aterrada.
Ela possui margens pois:
$$
M(u,1)=u
$$
e
$$
M(1,v) = v
$$
Agora, para mostrar que é 2-crescente, precisamos que:
$$
V_M(B)\ge0
$$
então, obtemos a desigualdade:
$$
\min(u_2,v_2)-\min(u_2,v_1)-\min(u_1,v_2)+\min(u_1,v_1)\ge0
$$
Se considerarmos os intervalos que formam o retângulo $B$ como intervalos para altura e base:
$$
I_a = [v_1,v_2]
$$
$$
I_b = [u_1,u_2]
$$
podemos dizer que a função $V_M(B)$ mede o tamanho da sopreposição desses intervalos na reta real.
Essa intersecção é dada pelo intervalo $[\max(u_1,v_1),\min(u_2,v_2)]$. Como a intersecção pode ser nula também, obtemos uma fórmula alternativa para $V_M$:
$$
V_M(B)=\max(0,\min(u_2,v_2)-\max(u_1,v_1))
$$
Provando então que a função é 2-crescente.

- $W(u,v)=\max(u+v-1,0)$
Novamente, é facil notar que a função é aterrada e possui margens.
Precisamos apenas provar que a função é 2-crescente.
Considere os termos
$$
u_2+v_2-1=a
$$
$$
u_2+v_1-1=b
$$
$$
u_1+v_2-1=c
$$
$$
u_1+v_1-1=d
$$
Por definição de dos valores, temos que $a>b$, $a>c$, $a>d$, $b>d$, $c>d$.
Por conta dessas desigualdades, podemos observar alguns casos a respeito de $V_W(B)$.
Como
$$
V_W(B) = \max(a,0) - \max(b,0)-\max(c,0)+\max(d,0)
$$
Caso $\max(d,0)=0$, temos $V_W(B)=-u_1-v_1+1=-d\ge0$ 
Caso $\max(b,0)=0$, temos $V_W(B)=u_2-u_1\ge0$
Caso $\max(c,0)=0$, temos $V_W(B)=v_2-v_1\ge0$
Caso $\max(b,0)=\max(c,0)=0=0$, temos $V_W(B)=\max(a,0)$
Para $V_W(B)=\max(a,0)$, se $a<0$, $V_W(B)=0$. Se $a>0$, então $V_W(B)=a>0$.
Assim, $W(u,v)$ é 2-crescente.

- $\Pi(u,v)=uv$
Novamente, é facil notar que a função é aterrada e possui margens.
Precisamos apenas provar que a função é 2-crescente.
Sendo
$$
V_\Pi(B)=u_2v_2-u_2v_1-u_1v_2+u_1v_1
$$
Podemos fatorar a expressão como
$$
V_\Pi(B)=(u_2-u_1)(v_2-v_1)
$$
que é maior ou igual a 0. Desse modo, $\Pi(u,v)$ é 2-crescente.


# Exercício 2.3
## a
Sendo 
$$
C_2(u,v) = (1-\theta)C_0(u,v)+\theta C_1(u,v)
$$
a media ponderada de duas copulas, vemos que $C_2$ é aterrada e possui margens.
Como $C_0$ e $C_1$ são não-decrescentes em cada um de seus argumentos, temos que 
$$
V_{C_2}(B)\ge0
$$Então, $C_2$ é uma cópula.
Vemos que esse comportamento se extende para qualquer quantidade de termos da média aritimética ponderada. Então a combinação convexa $C_n(u,v)$, composta por $n$ copulas, sempre será também uma copula.

## b
Consideramos a média geométrica entre as copulas $\Pi$ e $W$.
$$
C(u,v)=\sqrt{\Pi(u,v) W(u,v)}
$$
Considerando o retângulo $B=[1/2,3/4]\times[1/2,3/4]$, vamos observar seu $C$-volume.
$$
V_C(B)=\sqrt{\Pi(u_2,v_2) W(u_2,v_2)}-\sqrt{\Pi(u_2,v_1) W(u_2,v_1)}-\sqrt{\Pi(u_1,v_2) W(u_1,v_2)}+\sqrt{\Pi(u_1,v_1) W(u_1,v_1)}
$$
$$
V_C(B)=\sqrt{(9/32)}-\sqrt{12/32}\lt0
$$
Assim, a média geométrica não é uma copula.


# Exercício 2.4
## a
**copulas da familia Fréchet**
Sendo 
$$
C_{\alpha,\beta}(u,v)=\alpha M(u,v)+(1-\alpha-\beta)\Pi(u,v)+\beta W(u,v)
$$
vemos que a soma dos coeficientes é $1$. Assim, $C_{\alpha,\beta}(u,v)$ se trata de uma combinação convexa e foi mostrado no exercício 2.3 que combinações convexas de copulas também são copulas.

## b
**copulas da familia Mardia**
Vemos que os coeficientes $\frac{\theta^2(1+\theta)}{2}$, $1-\theta^2$ e $\frac{\theta^2(1-\theta)}{2}$ somam 1. Assim, se trata de mais uma combinação convexa. 


# Exercício 2.8
## a
Sabemos que a seção diagonal de uma copula é dada por $\delta_C(t)=C(t,t)$.
Assim, devemos verificar que
$$
\max(2t-1,0)\le C(t,t)\le t
$$
Sabemos também que, para qualquer copula $C$, vale a desigualdade
$$
W(u,v)\le C(u,v)\le M(u,v)
$$
Para o caso da seção diagonal, temos:
$$
\max(t+t-1,0)\le C(t,t)\le \min(t,t)
$$
Logo
$$
\max(2t-1,0)\le \delta_C \le t \ \ \ \square
$$
