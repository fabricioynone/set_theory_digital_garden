Naturalmente, se espera que 
$$
1 + 1 + 1 +\dots = \aleph_0
$$
Isto é, a soma de 1 $\aleph_0$ vezes. Ou, mais geralmente, se somarmos $\kappa$ $\lambda$ vezes, temos
$$
\kappa + \kappa + \dots = \lambda \kappa
$$
Seguindo a definição dada em [[Aritmética Cardinal Básica]], definamos:

*Def.*: Seja $(A_i : i\in I)$ um sistema de conjuntos mutualmente disjuntos tal que, para todo $i\in I$, $|A_i| = \kappa_i$. Definimos, então, 
$$
\sum_{i\in I} \kappa_i =\left|\bigcup_{i\in I} A_i\right|
$$
Vimos anteriormente que para o caso $I = \{1,2\}$, a escolha dos conjuntos não importa, mas para provar isso para nossa generalização, precisaremos do AC.

**Lema**: Se $(A_i : i\in I)$ e $(B_i : i\in I)$ são sistemas de conjuntos mutualmente disjuntos tais que $|A_i| = |B_i|$ para todo $i \in I$, então $\left|\bigcup_{i\in I} A_i \right|= \left|\bigcup_{i\in I} B_i\right|$.
*Dem.*: Para todo $i \in I$, tome uma função $f_i$ de $A_i$ em $B_i$ bijetora, que é possível considerando o produto cartesiano e o axioma da compreensão. Então, $f = \bigcup_{i\in I}f_i$ é uma bijeção entre $\bigcup_{i\in I} A_i$ e $\bigcup_{i\in I} B_i$.

Segue pela associatividade da união dos conjuntos que a soma de cardinais é também associativa e tem, também, propriedades razoáveis:

**Lema**: Se $\kappa_i \leq \lambda_i$ para todo $i \in I$, then $\sum_{i\in I}\kappa_i \leq \sum_{i\in I}\lambda_i$.
*Proof*: Como $\kappa_i \leq \lambda_i$, tomamos uma coleção disjunta $(B_i: i \in I)$ tal que $|B_i| = \lambda_i$ e $(A_i : i\in I)$ tal que $|A_i| = \kappa_i$ e $A_i \subseteq B_i$. Fica claro que $\bigcup_{i\in I}A_i \subseteq \bigcup_{i\in I} B_i$.

**Lema**: Se $\kappa_i = \kappa$ para todo $i\in \lambda$, então $\sum_{i\in I}\kappa_i = \lambda\kappa$.
*Proof*: Consideremos $(\{i\}\times A_i : i \in I)$, tal que $\kappa_i = |\{i\}\times A_i|$, temos que $\sum_{i\in I}\kappa_i = |\lambda\times\kappa|$ = $\kappa\times \lambda$

**Teorema**: Seja $\lambda$ um cardinal infinito, tome $\kappa_\alpha (\alpha < \lambda)$ cardinais não nulos e $\kappa = \sup\{\kappa_\alpha :\alpha < \lambda\}$. Então:
$$
\sum_{\alpha < \lambda}\kappa_\alpha = \lambda\kappa
$$
*Proof*: $\kappa_\alpha \leq \kappa$ para cada $\alpha < \lambda$, então $\sum_{\alpha < \lambda}\kappa_\alpha \leq \sum_{\alpha < \lambda}\kappa = \kappa\lambda$. Também temos que $\lambda = \sum_{\alpha < \lambda}1 \leq \sum_{\alpha<\lambda}\kappa_\alpha$.
Como a soma é um upper bound, temos que $\kappa \leq \sum_{\alpha < \lambda}\kappa_\alpha$. Juntando, temos que $\lambda\kappa \leq \sum_{\alpha< \lambda}\kappa_\alpha$, pois a multiplicação é o menor deles. Por Cantor-Bernstain, a prova se conclui.

**Corolário**: Se $\kappa_i (i\in I)$ são cardinais e se $|I| \leq\sup\{\kappa_i : i \in I\}$, então
$$
\sum_{i\in I} \kappa_i = \sup_{i\in I} \kappa_i
$$
Agora, vamos generalizar o produto de cardinais.

*Def.*: Tome $(A_i : i\in I)$ uma família de conjuntos tais que $|A_i| = \kappa_i$ para todo $i\in I$. Definimos o produto de $(\kappa_i : i\in I)$ por
$$
\prod_{i\in I}\kappa_i= \left|\prod_{i\in I} A_i\right|
$$
é sempre claro do contexto se o símbolo de produtório significa o produto de cardianais ou o produto cartesiano. 

**Lema**: Se $(A_i : i\in I)$ e $(B_i : i \in I)$ são tais que $|A_i| = |B_i|$ para todo $i \in I$, então, $\left|\prod A_i\right| = \left|\prod B_i \right|$.
*Proof*: Para cada $i \in I$, tomemos uma bijeção $f_i$ de $A_i$ para $B_i$, então, definimos $f$ uma função que para cada $x = (x_i : i\in I) \in \prod A_i$ nos dá $f(x) = (f_i(x_i) : i \in I)$.

É fácil ver que o produto é associativo, que se algum $\kappa_i = 0$, então o produtório é nulo e que se $\kappa_i \leq \lambda_i$ então $\prod \kappa_i \leq \prod \lambda_i$ e que $\prod \kappa = \kappa^\lambda$.

**Lema**: $(\prod_{i\in I}\kappa_i)^{\lambda} = \prod_{i\in I}(\kappa_i)^{\lambda}$ e $\prod \kappa^{\lambda_i} = \kappa^{\sum_{i\in I} \lambda_i}$.
*Proof*:

Produtórios infinitos são mais difíceis de avaluar do que somas infinitas. Em alguns casos especiais, porém, 

**Teorema (König's)**: Se $\kappa_i$ e $\lambda_i$ $(i \in I)$ são números cardinais e se $\kappa_i < \lambda_i$ para todo $i\in I$, então
$$
\sum_{i\in I}\kappa_i < \prod_{i\in I}\lambda_i
$$
*Proof*: 
>Estratégia de prova: Construir uma injeção para mostrar a desigualdade e provar que é estrita tomando um elemento que não está no membro da direita

Mostremos primeiro que $\sum_{i\in I}\kappa_i \leq \prod_{i\in I}\lambda_i$. Seja $|A_i| = \kappa_i$ e $|B_i| = \lambda_i$ para todo $i \in I$ e $A_i$ são mutualmente disjuntos. Podemos assumir, também, que $A_i \subseteq B_i$ e mostremos uma injeção de $\bigcup A_i$ para $\prod B_i$.
Escolhamos um $d_i \in B_i\setminus A_i$ para cada $i \in I$ e definamos para cada $x\in \bigcup A_i$, $i_x$ sendo o único $i\in I$ tal que $x\in A_i$. Assim, tomamos $f(x) = (a_i : i\in I)$ no qual
$$
a_i = \begin{cases}
x, \text{ se } i = i_x \\
 d_i, \text{ se } i \neq i_x
\end{cases}
$$
Provemos, agora, que o que montamos é uma injeção. Se $x \neq y$, então $f(x) = a$ e $f(y) = b$. Se $i_x = i_y = i$, então $a(i) = x$ e $b(i) = y$, logo, são diferentes. Caso contrário, $i_x \neq i_y$, então $a(i_x) \in A_{i_x}$ mas $b(i_x) \neq A_{i_x}$, logo, $f(x) \neq f(y)$.
Mostremos, agora, que é estrito. Se $\prod \lambda_i = \sum\kappa_i$, poderíamos achar subconjuntos mutualmente disjuntos $X_i$ do produto cartesiano $\prod B_i$ tal que $|X_i| = \kappa_i$ para todo $i$ e $\bigcup X_i = \prod B_i$. Mostremos que é impossível.
Tomemos, para cada $i\in I$, $A_i = \{a(i) :a\in X_i\}$, para cada $i\in I$, teremos $A_i \subseteq B_i$, como $|A_i|\leq |X_i| = \kappa_i < \lambda_i = |B_i|$, assim, existe $b_i \in B_i$ tal que $b_i \neq A_i$. Seja $b = (b_i: i\in I)$, assim, $b_i \neq A_i$ e, portanto, $b\neq X$, assim, $\bigcup X$ não é todo $\prod_{i\in I}B_i$.

Esse teorema é uma generalização do teorema de Cantor que diz que $A \preceq \mathcal P(A)$:
$$
\kappa = 1 + 1 +\dots, \kappa\text{ vezes}
$$
$$
2^\kappa = 2 \cdot 2\cdot\dots, \kappa\text{ vezes}
$$
Aplicando König, temos que $\sum_{i\in \kappa} 1 < \prod_{i\in \kappa} 2$

