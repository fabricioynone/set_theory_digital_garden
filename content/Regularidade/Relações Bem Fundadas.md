Por *relação definida própria* queremos nos referir, no presente texto, a um símbolo de predicado binário da linguagem em uso, seja ele primitivo (como $\in$) ou inserido por definição. Já o termo *relação definida* se refere a uma relação definida própria ou uma relação-conjunto.

*Def.*: Uma relação definida $R$ é dita set-like se, para todo $x$, existir um (único) conjunto $y$ tal que, para todo $z$, $zRx$ se, e somente se, $z \in y$. Ou seja, se 
$$
pred_R(x) = \{z : zRx\}
$$
é um conjunto para todo $x$. 
Dado um conjunto $X$, um elemento $x\in X$ é dito $R$-minimal se, e somente se, para todo $y\in X$, $y\not R x$. $R$ é dita bem fundada se todo conjunto não vazio possui um elemento minimal $R$-minimal. Em símbolos,
$$
\forall X(X \neq \emptyset \to\exists x\in X\forall y(
y\in X \to y\not R x
))
$$
Notemos que quando $R$ é definida própria, a definição acima é um esquema de definições, uma vez que para cada predicado $R$, temos uma definição do que significa $R$ ser set-like e bem fundada.
Notemos, também, que toda relação conjunto é set-like, uma vez que $pred_R(x) \subseteq dom R$.
A seguir, exporemos alguns exemplos.

*Exemplos*: 
-  $\in$ é set-like, pois $pred_\in(x) = \{y: y\in x\}$ é um conjunto.
- $\preceq$ não é set-like, pois para todo $x$, $\{x\} \preceq 1$, assim, $pred_\preceq(1)$ seria o conjunto de todos os singletos, que não existe.
- $\subseteq$ é set-like se, e somente se, vale o Axioma da Potência. Nesse caso, temos que $pred_\subseteq(x) = \mathcal P(x)$.
- = é set-like, pois $pred_=(x) = {x}$. Não, é, porém, bem-fundada, pois não possui um elemento =-minimal, uma vez que $x = x$. Analogamente, nenhuma relação reflexiva é bem-fundada
- $<$ ordenação para ordinais é set-like, pois $<$ é $\in|_{ON}$. Se $x$ é não vazio, todo elemento de $X$ que não é ordinal é minimal, senão, existe $\alpha = \min X$ e este será o $<$-minimal, pois $\forall \beta \in X, \alpha \leq \beta$, assim, $\neg(\beta < \alpha)$.

**Prop.**: Sejam $R$ e $S$ relações definidas tais que, para todo $x$ e $y$, se $xRy$, então $xSy$ (o que pode se abreviar por $R \subseteq S$), temos:
- i) Se $S$ é set-like, $R$ é set-like
- ii) Se $S$ é bem fundada, então $R$ é bem fundada.
*Proof*: i) Para todo $x$, $pred_R(x) = \{y\in pred_S(x) : yRx\}$
ii) Seja $A$ um conjunto não-vazio. Seja $m\in A$ um elemento $S$-minimal de $A$. Então, $m$ é um elemento $R$-minimal de $A$, pois, se $yRm$, então $ySm$ e, portanto, $y\notin A$.

*Def.:* Seja $R$ uma relação definida. Para cada natural $n \geq 1$ e cada par $a, b$, um $R$-caminho de $n$ passos de $a$ até $b$ é uma sequência de elementos $(x_0,\dots,x_n)$ tal que $x_i Rx_{i+1}$ para todo $i \lt n$, no qual $x_0 = a$ e $x_n = b$.
Define-se $R^*$ por $xR^*y$ se, e somente se, existe um $R$-caminho com $n$ passos para algum natural $n \geq 1$ que começa com $x$ e termina com $y$.

Dizemos que $R^*$ é o fecho transitivo de $R$, ou a transitivização de $R$, veremos o porquê na próxima proposição.
Atendando novamente, quando $R$ é próprio, a definição anterior e as proposições seguintes viram esquemas de proposições. Já se forem relações-conjunto, cada uma pode ser escrita como única sentença na linguagem.

**Prop.**: Se $R$ é uma relação definida, então $R^*$ é uma relação transitiva que estende $R$. 
*Proof*: É claro que se $xRy$, então $xR^*y$ pelo caminho $(x,y)$, logo, $R^*$ é extensão de $R$. Para transitividade, basta unir os caminhos.

Dado $R$, o fecho é a menor relação transitiva que contém $R$.

**Prop.**: Se $R$ é uma relação definida set-like, então $R^*$ é uma relação definida set-like.
*Proof*: Seja $x$ um conjunto qualquer. Provemos por indução em $n \geq 1$, que para todo $n\in \omega$ existe um único conjunto $pred_R^n(x)$ que contém apenas todos os elementos que possuem um $R$-caminho de $n$ passos até $x$.
Para a base, $n = 1$, temos $pred_R^1(x) = pred_R(x)$. Suponha, agora, que vale para $n \geq 1$. Provemos que implica que vale para $n + 1$. Pelo Esquema da Substituição, $\{pred_R(y) : y\in pred_R^n(x)\}$ é bem definido. Definamos, então, $prod_R^{n+1}(x) = \bigcup\{pred_R(y) : y\in pred_R^n(x)\}$. Mostremos que vale o que queremos.
Se $z \in pred_R^{n+1}(x)$, então $z\in pred_R(y)$ para algum $y\in pred_R^n(x)$, assim, existe um $R$-caminho $(x_0,\dots,x_n)$ de $n$ passos de $x_0 = y$ a $x_n = x$ com $zRy$, obtemos, assim, $(z,y,\dots,x_n)$ um caminho de $n + 1$ passos de $z$ a $x$. (Todos elementos do conjunto que cosntruímos possuem um $R$-caminho de tamanho $n + 1$ para $x$)
Reciprocamente, tomemos um $R$-caminho $(x_0,\dots,x_{n+1})$ de $n + 1$ passos. Sabemos que $x_1 \in pred_R^n(x)$. Como $x_0Rx_1$, $x_0 \in pred_R(x_1)$, assim, $x_0\in pred_R^{n+1}(x)$. (Todo elemento que possui um $R$-caminho de tamanho $n+1$ está no conjunto que construímos).
Pelo Esquema da Substituição, considere $Z = \bigcup_{ 0 < n\in \omega} pred_R^n(x)$. Temos, assim, que $z \in R^*x \Longleftrightarrow z \in Z$.

*Def.:* Seja $R$ uma relação definida e $A$ uma classe. A restrição de $R$ a $A$, denotada por $R_A$, é definida por:
$$
\forall x\forall y(xRy\land x\in A\land y\in A)
$$
Quando $A$ é um conjunto, $R_A = \{(x,y) \in A\times A : xRy\}$.
Dizemos que $R$ é bem-fundada em $A$ se, e somente se, $R_A$ é bem-fundada.


se pa incompleto