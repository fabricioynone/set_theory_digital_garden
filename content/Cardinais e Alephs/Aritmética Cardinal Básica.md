É possível definir operações de aritmética cardinal e elas não coincidem com a noção de aritmética ordinal.

*Def.*: Sejam $\kappa$ e $\lambda$ cardinais. Define-se $\kappa + \lambda$ como $|\{0\}\times\kappa\cup \{1\}\times \lambda|$ e $\kappa\cdot\lambda$ como $|\kappa\times\lambda|$.

Note que é bem definido pois ambos conjuntos são bem ordenáveis. (Pergunta, o que é necessário para que sejam bem ordenáveis ???)

*Exemplo*: Na soma ordinal temos que $\omega+\omega > \omega$. Já na cardinal, obtemos que $\omega + \omega = |\{0\}\times\omega\cup\{1\}\times\omega| = \omega$.

Seguem alguns lemas sobre a operação que definimos.

**Lema**: Seja $A$ um conjunto e suponha que exista $B$ bem ordenável tal que $f: B \to A$ é uma sobrejeção. Então, $A$ é bem ordenável e $A \preceq B$.
*Proof*: Construamos a boa ordenação. Seja $<_B$ a boa ordenação em $B$, vamos definir $g: A \to B$ dada por $g(a) = \min\{b\in B : f(b) = a\}$ para todo $a \in A$, pela unicidade do mínimo e por $B$ sobrejetar em $A$, $g$ é bem definida e é claramente injetora. Definamos, agora, a relação em $A$:
$$
x <_A y \Longleftrightarrow g(x) <_B g(y)
$$
Como $g: (A, <_A) \to (g[A], <_B)$ é isomorfismo, vale que $A$ é bem ordenável.

**Lema**: Sejam $A$ e $B$ conjuntos bem ordenáveis disjuntos. Então, $|A\cup B| = |A| + |B|$.
*Proof*: Como são disjuntos, vale que $A \cup B \approx \{0\}\times A \cup \{1\}\times B$, segue, então, a igualdade que queremos.

**Lema**: Sejam $\kappa, \kappa',\lambda,\lambda'$ cardinais tais que $\kappa \leq \kappa'$ e $\lambda \leq \lambda'$. Então, $\kappa + \lambda \leq \kappa'+ \lambda'$ e $\kappa\cdot\lambda \leq \kappa'\cdot\lambda'$.
*Proof*: Para a soma, notemos que $\{0\}\times \kappa \cup \{1\} \times \lambda \subseteq \{0\}\times \kappa' \cup \{1\} \times \lambda'$. Assim segue o resultado que queremos. Para multiplicação, é análogo.

**Lema**: $A$ e $B$ bem ordenáveis. Então, $A \cup B$ é bem ordenável e $|A\cup B| \leq |A| + |B|$.
*Proof*: Seja $B' = A\setminus B$, temos que $A \cup B' = A \cup B$ é bem ordenado (podemos fazer isso com uma ordenação análoga a lexicográfica). Como $|B'| \leq |B|$, temos:
$$
|A \cup B| = |A\cup B'| = |A| + |B '|\leq |A| + |B|
$$

**Lema**: Sejam $\kappa$ e $\lambda$ cardinais. Então $\kappa + \lambda = \lambda + \kappa$ e $\kappa \cdot \lambda = \lambda \cdot \kappa$.
*Proof*: $\kappa + \lambda = |\{0\}\times \kappa\cup\{1\}\times \lambda| = |\{1\}\times \kappa\cup\{0\}\times \lambda| = \lambda + \kappa$. Basta tomar a função que swapa os índices e ver que é bijeção.
Analogamente para o produto, tomando a função que leva $(x,y) \to (y,x)$.

**Lema**: Sejam $\kappa$ e $\lambda$ cardinais tais que $2 \leq \kappa$ e $2\leq \lambda$. Então, $\kappa + \lambda \leq \kappa\cdot\lambda$.
*Proof*: Se $\max\{\kappa,\lambda\} = \lambda$, então:
$$
\{0\}\times \kappa \cup \{1\} \times \lambda \subseteq \kappa \times \lambda
$$
e segue o resultado. Caso contrário, aplicamos o lema anterior o o mesmo argumento.

**Teorema**: Sejam $\kappa$ e $\lambda$ cardinais infinitos. Então, $\kappa + \lambda = \kappa\cdot\lambda = \max\{\kappa,\lambda\}$. 
*Proof*: Seja $\mu = \max\{\kappa,\lambda\}$, $\mu \preceq \kappa + \lambda \implies \mu \leq \kappa + \lambda$. Temos:
$$
\mu \leq \kappa + \lambda \leq \kappa\cdot\lambda \leq \mu\cdot\mu  = \mu
$$
Usando o teorema que vimos em [[Quadrados de Cardinais]].

**Corolário**: $n$ cardinal finito e $\kappa$ um cardinal infinito. Então:
- a) $n + \kappa = \kappa + n = \kappa$;
- b) $n\cdot \kappa = \kappa \cdot n = \kappa$, se $n \neq 0$;
- c) $0 \cdot \kappa = \kappa \cdot 0 = 0$.
*Proof*: a) $\kappa \leq n + \kappa \leq \kappa + \kappa = \kappa$
b) $\kappa \leq n\cdot \kappa \leq \kappa \cdot \kappa = \kappa$
c) Segue pela definição.

**Lema**: $m,n$ cardinais finitos, isto é, naturais. Então a soma e multiplicação da aritmética cardinal coincidem com a soma e multiplicação dos naturais.
*Proof*: $$