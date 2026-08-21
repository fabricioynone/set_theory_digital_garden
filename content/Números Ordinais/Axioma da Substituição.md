## Motivação 
Para mostrar que toda boa ordem é isomorfa a um ordinal, precisaremos do axioma da substitição. Antes de enunciá-lo e, com ele alguns resultados, vamos motivar a sua necessidade.

Considere $(I, <_{I})$ uma boa ordem e, para cada $i\in I$, considere $(A_i,<_{A_i})$ boas ordens. É fácil de ver que $U_{i\in I}\{i\}\times A_i$ é uma boa ordem para ordenação dada por:
$$
(i,a) < (j,b) \Longleftrightarrow i<_I j \lor(i = j \land a<_{A_i} b)
$$
Em particular, para  $I = 2$ com a boa ordem $0<1$, temos que o conjunto $\{0\}\times \omega \cup \{1\}\times \omega$ é uma boa ordenação, porém, não é muito claro qual é o ordinal isomorfo a esta boa ordem.
Notemos que $\{0\}\times \omega \cong \omega$, e que $\{0\}\times \omega \cup \{1\}\times\{0\}\cong \omega + 1$, $\{0\}\times \omega \cup \{1\}\times\{0,1\}\cong \omega + 2$ e assim por diante. Podemos, formalizar, então, $\omega + n$ usando o axioma do par, fazendo $S^n(\omega) = \omega + n$.
Porém, observando o conjunto o qual queremos descobrir seu análogo nos ordinais, teríamos, algo como $\omega + \omega$, que não podemos provar a existência usando apenas as ferramentas que temos agora o que temos agora (aparentemente, podemos provar a não existência usando modelos).
Consideremos, então:
## Axioma da Substituição

**Axioma (da Substiuição)**: Para cada fórmula $\phi(x,y,A,t_1,\dots,t_n)$, a seguinte fórmula é um axioma
$$
\forall t_1\dots\forall t_n \forall A (\forall x\in A\exists!y\phi(x,y,A,t_1,\dots,t_n) \rightarrow\exists B\forall y(\exists x\in A(\phi(x,y,A,t_1,\dots,t_n) \rightarrow y\in B)))
$$

Fixado $t_1,\dots,t_n,A$, seja uma $\phi$ fórmula que, para cada $x \in A$ exista apenas um $y$ tal que $\phi(x,y,A,t_1,\dots,t_n)$, então existe um conjunto $B$ que contém todos estes $y$. Claro, o axioma não garante que $B$ contenha apenas os $y$, mas isso pode ser facilmente resolvido usando o axioma da compreensão.

## Substituição Compreendida

**Prop. (Substituição Compreendida)**: Para cada fórmula $\phi(x,y,A,t_1,\dots,t_n)$, a seguinte fórmula é um teorema:
$$
\forall t_1\dots\forall t_n \forall A (\forall x\in A\exists!y\phi(x,y,A,t_1,\dots,t_n) \rightarrow\exists B\forall y(\exists x\in A(\phi(x,y,A,t_1,\dots,t_n) \leftrightarrow y\in B)))
$$
*Prova*: Dados $t_1,\dots, t_n$ e $A$ tais que $\forall x\in A\exists!y\phi(x,y,A,t_1,\dots,t_n)$, sabemos que existe um $B'$ tal que $\forall y(\exists x\in A(\phi(x,y,A,t_1,\dots,t_n) \leftrightarrow y\in B'))$, pelo axioma da compreensão, podemos tomar
$$
B = \{y\in B': \exists x\in A\phi(x,y,A,t_1,\dots,t_n)\}
$$
Obtemos, então, a fórmula desejada. 

Note que o conjunto $B$ é único pelo Axioma da Extensionalidade.

## Thm: Toda ordem é isomorfa a um único ordinal

**Def.**: Seja $F(x,t_1,\dots,t_n,)$ um símbolo introduzido por definição de modo que para alguma fórmula $\phi(x,t_1,\dots,t_n,y)$, temos 
$$
\forall t_1,\dots,\forall t_n\forall x \exists!y(\phi(x,t_1,\dots,t_n,y)
$$
e
$$
\forall t_1\dots\forall t_n\forall x\forall y(F(x,t_1,\dots,t_n) = y \leftrightarrow \phi(x,t_1,\dots,t_n,y))
$$
Dados $t_1,\dots,t_n, A$, o único conjunto $B$ tal que $\forall y(\exists x\in A(\phi(x,y,A,t_1,\dots,t_n) \leftrightarrow y\in B)$ é denotado como $F_{t_1,\dots,t_n}[A] = \{F_{t_1,\dots,t_n}(x): x\in A\}$.

Tendo as ferramentas e notação em mãos, podemos provar o que queríamos:

**Teorema**: Para toda boa ordem $A$, existe um único ordinal $\alpha$ tal que $\alpha \cong A$.
*Prova*: A unicidade segue do lema que podemos encontrar que [[Números Ordinais]], que afirma que para $\alpha$ e $\beta$ ordinais, se $\alpha \cong \beta\implies \alpha = \beta$.
Vamos provar a existência. Consideremos, então, $F(P,a)$ um símbolo de função introduzidpo por definição como:
$$
F(P,a) = \begin{cases}
\alpha, \text{ se } \exists A, <
(P = (A, <) \text{ É uma boa ordem, } a\in A\text{ e } \alpha \text{ é um ordinal isomorfo a } A[A]) \\
 \emptyset, \text{ caso contrário}
\end{cases}
$$
Dada uma boa ordem $P = (A,<)$, considere $X = \{a\in A : \exists \alpha(\alpha \cong A[a])\}$ e $\alpha = F_P[X]$ e $f = F_P\upharpoonright X$. Notemos que $X$ é um conjunto válido por causa do axioma da substuição, usando a unicidade que comentamos no parágrafo anterior.
Provaremos que $f$ é nosso isomorfismo. Para isso, notemos:
- (i) $X$ é um segmento inicial.
- (ii) $f$ é crescente.
De fato, dado $b\in X$ e $a\in A$ tal que $a<b$, seja $\beta$ o ordinal isomorfo a $A[b]$ e $g: A[b] \to \beta$ o isomorfismo. Temos que $g\upharpoonright A[a] \to \beta[g(a)]$ é um isomorfismo (lema de [[Boas Ordens]]). Analisemos $\beta[g(a)] = \{\gamma \in \beta : \gamma < g(a)\} = g(a)$, assim, $a\in X$, provando (i), e $f(a) = g(a) < g(b) = \beta$, provando (ii).
Ademais, $\alpha$ é um ordinal. De fato, com é um conjunto de ordinais, basta mostrar que é transitivo. Seja $\beta \in \alpha$ e $\xi \in \beta$. Tomemos $a\in A$ tal que $g(a) = \xi$, sabemos que existe, pois existe um isomorfismo de um segmento inicial próprio de $A$ e $\beta$. Isto é, seja $b\in A$ tal que $g: A[b] \to \beta$ é um isomorfismo, sabemos que $g\upharpoonright_{A[a]}: A[a]\to \beta[g(a)]$ é um isomorfismo. Notemos, analogamente ao anterior, que $\beta[g_a] = \beta[\xi] = \{\gamma\in \beta: \gamma<\xi\} = \xi$, logo, $a\in X$ e, portanto, $\xi\in \alpha \implies \beta\subseteq\alpha$. Assim, $\alpha$ é transitivo e, poranto, um ordinal.
Como $f:X\to \alpha$ é estritamente crescente e sobrejetora, $f$ é um isomorfismo. Vamos provar que $X = A$ mostrando que $X$ não pode ser segmento inicial próprio de $A$. Assuma que seja, então existe $a \in A$ tal que $X = A[a]$. Por definição, $a\not\in A$. Porém, $f:A[a]\to \alpha$ é um isomorfismo, logo, $a\in X$, absurdo. 
Concluímos, então, que $f$ é um isomorfismo de $A$ a um ordinal $\alpha$.

*Remark*: Não poderíamos definir $X$ sem substituição pois, por exemplo, sabemos que não há um conjunto que contenha todos os ordinais, como visto em [[Números Ordinais]].

## Tipo de boa ordem

Podemos definir, então:
**Def.**: Seja $A$ uma boa ordem, o tipo de $A$, denotado $tp(A)$, é o único ordinal isomorfo a $A$.
