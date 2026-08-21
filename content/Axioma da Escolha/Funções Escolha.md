*Def.*: Seja $\mathcal C$ uma coleção de conjuntos não vazia. Uma função escolha para $\mathcal C$ é uma função $c$ de de domínio $\mathcal C$ tal que $\forall c\in C, \, c(a) \in a$.

Seja $X$ um conjunto, uma partição de $X$ é um conjunto $P$ de subconjuntos de $X$ tais que os elementos de $P$ são dois a dois distintos e $\cup P = X$.

*Def.*: Seja $X$ conjunto e $P$ partição de $X$. Um conjunto transversal para $P$, ou o conjunto de representantes para $P$ é um subconjunto $T$ de $X$ tal que vale que $\forall a\in P ,\,T\cap a$ é um conjunto unitário.

*Def.*: Seja $(A_i : i\in I)$ uma família indexada de conjuntos não vazios. Uma função escolha indexada para $(A_i : i\in I)$ é uma função de domínio $I$ tal que $\forall i\in I, \, c(i) \in A_i$.

Se $A_i$ é vazio, não há restrição sobre o valor de $c(i)$.

**Prop.**: São equivalentes:
- a) Para todo conjunto $X$ e toda partição $P$ de $X$, existe um conjunto transversal para $P$.
- b) Para toda família indexada $(A_i : i\in I)$ de conjuntos não vazios, existe uma função de escolha indexada para $(A_i : i \in I)$. 
- d) Para toda coleção de conjuntos não vazios $\mathcal C$, existe uma função escolha para $\mathcal C$.
*Proof*: a) $\implies$ b) Considere $(A_i : i\in I)$ uma família indexada de conjuntos. Tomemos $X = \bigcup_{i\in I}\{i\}\times A_i$. Seja $T \subseteq X$ o conjunto transversal de $X$, sabemos que é tal que $\forall i \in I (T\cap\{i\}\times A_i)$ é um conjunto unitário. Então, temos $T: I \to \bigcup_{i\in I} A_i$ é uma função escolha.
b) $\implies$ c) Seja $\mathcal C$ uma coleção de conjuntos não vazia. Tomemos $I = C$ e consideremos a família $(A_a : a\in I)$ dada por $A_a = a$. Seja $f: \mathcal C \to \bigcup_{a\in C} a$ a função escolha indexada para a familía $(A_a : a\in I)$. Temos que, $\forall a\in C, \, f(a) \in A_a = a$, logo, $f$ é função escolha para $\mathcal C$.
c) $\implies$ a) Seja $X$ um conjunto e $P$ uma partição de $X$. Seja $f: P \to X$ uma função escolha para $P$. Então, $T = f[P]$ é como desejado.

**Axioma (da Escolha)**: Para toda partição $P$, existe um conjunto $T$ que intersecta cada elemento de $P$ em um conjunto unitário. Em símbolos,

$$
\forall P(\forall a,b\in P (a\neq b \to \not\exists x (x\in a \land x\in b))\to \exists T \forall a \in P\exists!x (x\in T \land x\in a))
$$

Alguns apontamentos para a necessidade do axioma da escolha, é que ele começa a ser necessário quando falamos de conjuntos infinitos já que vale que:

**Teorema**: Todo conjunto finito tem uma função escolha
*Proof*: Pode ser feita facilmente usando indução.

O problema é que não podemos garantir que podemos fazer infinitas escolhas arbitrárias.