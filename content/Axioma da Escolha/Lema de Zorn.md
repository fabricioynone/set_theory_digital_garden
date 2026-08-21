Veremos que o axioma da escolha é equivalente ao lema de Zorn.

**Teorema (Lema de Zorn)**: Seja $(P,\leq^*)$ uma pré-ordem tal que toda cadeia é limitada superiormente, então $P$ possui um elemento maximal.
*Proof*: 
> Estratégia de Prova: Supondo que não existe, podemos construir uma bijeção entre $|P|^+$ e $|P|$

Denotemos $<^*$ a ordem restrita dada por $a <^* b \Longleftrightarrow a\leq^* b\land b\not\leq^* a$. Seja $\kappa = |P|^+$. Suponhamos que não exista elemento maximal. Notemos, primeiro, que o vazio é uma cadeia de $P$, logo, tem cota superior e, portanto, é não vazio. Consideremos $g: \mathcal P (P)\setminus\{\emptyset\} \to P$ uma função escolha e $b \in P$. Definamos $f: \kappa\to P$ recursivamente por:
$$
f(\alpha) = \begin{cases}
g(\{p\in P : \forall \beta < \alpha, f(\beta) <^* p\}), \text{ se } \{p\in P : \forall \beta < \alpha, f(\beta) <^* p\}\neq \emptyset \\
b, \text{ caso contrário}
\end{cases}
$$
Verificaremos as seguintes coisas:
- a) $f(\alpha) = g(\{p\in P :  \forall \beta \lt \alpha, f(\beta) <^* p\})$, isto é, é sempre o primeiro caso
- b) $\forall \xi < \alpha, f(\xi) <^* f(\alpha)$, isto é, são diferentes
Provemos por indução transfinita. Suponha que vale para todo $\beta < \alpha$. Temos, para todos $\xi < \beta < \alpha$, temos que $f(\xi) <^* f(\beta)$, assim, todos $\beta \in \alpha$ são comparáveis, logo $A = \{f(\beta) : \beta < \alpha\}$ é uma cadeia em $P$. 
Por hipótese, $A$ tem limitante superior, isto é, existe $p'\in P$ tal que $f(\beta) \leq p'$ para todo $\beta < \alpha$. Como $p'$ não pode ser maximal de $P$, pois assumimos que não existe elemento assim, sabemos que $\{p\in P : \forall \beta < \alpha, f(\beta) <^* p\}$ é não vazio, então provamos que vale a). 
Segue de $f(\alpha) \in \{p\in P : \forall \beta < \alpha, f(\beta) <^* p\}$ que $f(\xi) < f(\alpha) \forall \xi < \alpha$ e, assim, está provado b).
Provamos, então, que $f$ é injetora, absurdo, pois, por definição, temos que $h(P) = \kappa \not\preceq P$.

Dois outras provas do teorema podem ser dadas com a mesma estrutura, mas omitindo que precisamos da segunda forma no teorema da recursão e omitindo o uso do axioma da escolha.

Assumindo apenas o Lema de Zorn, podemos provar o Axioma da Escolha.

**Teorema**: Lema de Zorn $\Longleftrightarrow$ Axioma da Escolha.
*Proof*: Vimos anteriormente que a volta.
> Estratégia de Prova: Considerar um conjunto de semi-transversais e usar o lema de Zorn para mostrar que o maximal desse conjunto é um conjunto transversal da partição dada

Seja $X$ um conjunto e $P$ uma partição de $X$. Consideremos:
$$
\mathbb P = \{T \subseteq X : \forall A\in P, T\cap P \text{ é unitário ou vazio}\}
$$
Segue das propriedades de inclusão que $(\mathbb P, \subseteq)$ é uma pré-ordem. Seja $\mathcal C$ uma cadeia de $\mathbb P$, queremos mostrar que tem limitante superior. Claramente, $T = \bigcup C$ é limitante superior pela inclusão, vejamos se está em $\mathbb P$. Claramente $T \subseteq X$, suponha que $\exists u, v \in A \cap T$, teremos que existem $R, S$ tais que $u \in R$ e $v \in S$, mas, por ser uma cadeia, temos que são comparáveis, ou seja, um está contido no outro. Suponha, sem perda de generalidade, que $R \subseteq S$, teríamos, então, que $u, v \in S \subseteq T$, o que implica que $S \cap T$ não é unitário nem vazio, absurdo.
Concluímos, assim, que toda cadeia tem uma cota superior. Pelo lema de Zorn, obtemos que existe um elemento maximal de $\mathbb P$. Seja $T$ esse conjunto, afirmamos que esse será o conjunto transversal. Se $\exists A \in P$ tal que $A\cap T = \emptyset$, tomemos $a \in A$ e vamos considerar $T'= T \cup \{a\}$, temos que $T \subsetneq T'$ e $T'\cap A = \{a\}$ e vale que para todo $B \in P$ $T '\cap B$ é vazio ou unitário, segue, assim, que $T'\in P$, mas $T \subseteq T'$, absurdo. 