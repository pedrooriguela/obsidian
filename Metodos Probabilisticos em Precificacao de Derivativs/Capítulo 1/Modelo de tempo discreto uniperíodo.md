# Definições básicas
Modelo uniperíodo designa um mercado com apenas um ativo de risco (ação). Essa ação pode ser comprada ou vendida em 2 tempos, $t_0$ e $t_1$. O preço do ativo em $t_0$ é $S_0$ e em $t_1$ ele pode ser:
$$
S_u, \ \ \ \ \text{com probabilidade }p_u
$$
$$
S_d, \ \ \ \ \text{com probabilidade }p_d = 1-p_u
$$
É acordado que $S_u > S_d$.
O mercado onde é negociada essa ação é definido por axiomas. **A evolução do preço da ação é determinado por**:
1) Os instantes $t_0$ e $t_1$, com $t_1>t_0$.
2) Valor inicial da ação $S_0$, em $t_0$. Os valores finais $S_u$ e $S_d$, em $t_1$, com $S_u>S_d$.
3) Probabilidade $p_u$ da ação subir para o preço $S_u$ e a probabilidade $p_d$ da ação descer para o preço $S_d$. $p_u, \ p_d > 0$ e $p_u + p_d = 1$.

**O comportamento do titular da ação é determinado pelo axioma**:
1) O titular age racionalmente. Ele só exerce a opção quando ela traz lucros, ou seja, exerce a opção de compra quando o preço final é menor que o preço inicial $K$ e só exerce a opção de venda quando o preço final é maior que o preço inicial $K$.

É necessário recordar que ações possuem preços em $t_0$, de modo que o lançador da ação recebe esse preço e o comprador paga.

**O comportamento dos agentes é determinado por**:
1) No modelo descrito, há um numero infinito de agentes. eles podem comprar ou vender qualquer quantidade de ações no momento $t_0$ e $t_1$. Eles podem realizar short sellings também.

A suposição de um market-maker que está sempre disposto a comprar e vender ações implica na existência de um super-agente, que nesse modelo será um banco.
**O banco funciona seguindo o seguinte axioma**:
1) Existe um banco no qual qualquer agente pode tomar emprestado ou investir no tempo $t_0$ para ser devolvida no tempo $t_1$ corrigida pela taxa de juros $r$. A quantia a ser resgatada ou devolvida, quando se investe ou toma emprestado uma quantia $x$, é representada por:
$$
	e^{r(t_1-t_0)}x
$$

Pode-se dizer que o problema central se baseia em, dados os parâmetros descritos acima, encontrar o valor correto do preço $C_0$ de certa ação. Resolver isso chama-se precificar uma opção.

## Exercício 2
Considerando o caminho incorreto de calcular $C_0$ sugerido pelo livro, utilizando o exemplo 1, $C_0$ deve ser igual à perda média do lançador da opção. Considerando que se queira precificar uma Call com preço de exercício $K=110$. 

Caso o preço suba para $125$, o lançador é obrigado a vender a ação por $110$, tendo uma perda de $15$.

Caso o preço caia para $95$, o lançador não possui prejuízo.

Logo, a perda média e $C_0$ são:
$$
C_0 = (0.6\times15)+(0.4\times0) = 9
$$

Logo, calculado de maneira incorreta, o preço de $C_0$ é $9$.

# Precificação de opções pelo hedging
O princípio real para calcular $C_0$ é diferente da ideia de apenas igualar os lucros médios do titular e do lançador da opção. O princípio se chama **hedging**.

Para começar a definição, são introduzidos $C_u$ e $C_d$ :
$$
C_u = \max{\{S_u-K, \ 0\}}, \ \ C_d = \max{\{S_d-K, \ 0\}}, \ \ \text{para opção de compra}
$$
$$
C_u = \max{\{K-S_u, \ 0\}}, \ \ C_d = \max{\{K-S_d, \ 0\}}, \ \ \text{para opção de venda}
$$
$C_u$ e $C_d$ são os preços da opção no tempo $t_1$ caso a ação suba ou desça, respectivamente. Uma vantagem de utilizar esses símbolos é que pode-se tratar opções de compra e venda de modo unificado.

Pode ser definido o preço/valor de uma opção em um tempo $t$ como a quantidade de dinheiro que o seu dono recebe se vendê-la no tempo $t$. É importante notar que os valores $C_u$ e $C_d$ são os valores exatos que o lançador precisa desembolsar no tempo $t_1$ para cumprir sua obrigação frente ao titular.

## Exemplo 3
Vamos considerar o modelo utilizado no **Exercício 2**, com $r=0$.
Ao assinar um contrato de opção de compra com $K=110$ o titular pagou ao lançador $C_0=2.5$.
O exemplo demonstrará como o lançador pode utilizar $C_0$ em $t_0$ para obter, em $t_1$ $C_u$ ou $C_d$ .

No tempo $t_0$, o lançador deve pegar emprestado $47,5$ do banco. Com $47,5 + C_0 = 50$, o lançador deve comprar $\frac{1}{2}$ ação. 
Em $t_1$, 