Além das vistas em [[Conjuntos Bem Ordenáveis]], temos várias outros resultados na matemática geral, isto é, fora da teoria dos conjuntos, que fazem uso do Axioma da Escolha.
Depois de algumas consequências para a teoria que estamos focando em, seguem alguns resultados da matemática, em geral, que usam o Axioma da Escolha.

(From Jech's)
## Axioma da Escolha na Teoria dos Conjuntos
**Teorema**: Todo conjunto infinito tem um subconjunto infinito enumerável.
*Proof*: Seja $A$ um conjunto infinito, pelo Axioma da Escolha, segue que ele é bem ordenável, então existe um ordinal $\alpha$ tal que $A \approx \alpha$. Seja $\phi$ o isomorfismo entre eles, sabemos que $\phi|_\omega: \omega \to A[\phi(\omega)]$ é um isomorfismo, logo, temos um subconjunto enumerável. 
*Comentário*: Jech usa enumerável como infinito enumerável. Esta noção continuará através desta nota, em particular.

**Teorema**: União enumerável de uma coleção de enumeráveis é enumerável.
*Proof*: Seja $S$ um conjunto enumerável de conjuntos enumeráveis, vamos definir $S = \bigcup A$. Como $S$ é enumerável, $S = \{A_n : n \in \omega\}$ com cada $A_n$ enumerável. Para cada $A_n$, sabemos que existe o conjunto de todas as sequências em $A_n$ e, usando o Axioma da Escolha, podemos escolher para cada $n\in \omega$, $s_n$ sequência em $A_n$. 
Podemos, portanto, definir $f: \omega \times \omega \to A$ dado por $f(n,k) = s_n(k)$, que é um maa sobrejetor, segue de $\omega\times \omega$ ser enumerável (e, portanto, todos seus subconjuntos) que $A$ é enumerável.

**Corolário**: O conjunto dos números reais não é união de conjuntos enumeráveis.
*Proof*: Os reais não são enumeráveis.

**Corolário**: O ordinal $\omega_1$ não é supremo de um conjunto enumerável de ordinais enumeráveis.
*Proof*: Tomemos $A =\{a_n : n \in \omega\}$ um conjunto de ordinais contáveis. Então, tomemos $\alpha = \sup A = \bigcup_{n \in \omega}a_n$ que é união de enumeráveis, logo, é enumerável. Assim, $\alpha < \omega$.

**Teorema**: $2^{\aleph_0} \geq \aleph_1$
*Proof*: Segue do fato que $2^{\aleph_0} > \aleph_0$.

**Teorema**: Seja $f$ uma função e $A$ um conjunto, temos que $|f[A]| \leq |A|$.
*Proof*: Para cada $b \in f[A]$ definamos $X_b = f^{-1}(\{b\})$, notemos que $X_b \neq \emptyset$ e que para $b_1 \neq b_2$, temos que $X_{b_1}\cap X_{b_2}$ é disjunto, decorrente do fato de $f$ ser função.
Tomemos $g \in \prod_{b\in f[A]}X_b$, então $g: f[A] \to A$ é uma injeção.

O próximo teorema é uma generalização do teorema que diz que a união enumerável de enumeráveis é enumerável.

**Teorema**: Seja $S$ uma coleção de conjuntos. Se $|S| \leq \aleph_\alpha$ e para todo $A \in S$ vale que $|A| \leq \aleph_\alpha$, então $|\bigcup S| \leq \aleph_\alpha$.
*Proof*: A prova é razoavelmente análoga ao que provamos anteriormente. Vamos assumir que $S \neq \emptyset$ e $\forall A \in S$, $A \neq \emptyset$. 
Podemos escrever, então, $S = \{A_\mathcal V : \mathcal V < \aleph_\alpha\}$, assim, para cada $\mathcal V < \aleph_\alpha$, usando o Axioma da Escolha, podemos tomar uma sequência transfinita sobrejetora em $a_\mathcal V = \langle a_\mathcal V(k) : k \in \aleph_\alpha\rangle$ e podemos definir $f: \aleph_\alpha \times \aleph_\alpha \to \bigcup S$ sobrejetora dado por $f(\mathcal V, k) = a_\mathcal V(k)$.
Segue pelo anterior que $|f[\aleph_\alpha \times \aleph_\alpha]| \leq |\aleph_\alpha \times \aleph_\alpha| = \aleph_\alpha$ e segue de $f$ ser sobrejeção que $|\bigcap S| \leq \aleph_\alpha$.

**Teorema**: Se $(A, \preceq)$ é ordenação linear tal que $|\{y \in A : y \preceq x\}| \leq \aleph_\gamma$ para todo $x \in A$, então $|A| \leq \aleph_\gamma$.
*Proof*:

## Uso do Axioma da Escolha na Matemática
**Prop. (Pontos de Aderência em $\mathbb R$)**: $A \subseteq \mathbb R$. $a \in \mathbb R$ é ponto de aderência de $A$, então existe $(a_n : n \in \omega)$ uma sequência de elementos de $A$ tal que $a_n \to a$.
*Proof*: Seja $g$ uma função escolha para $\mathcal P(\mathbb R)\setminus\{\emptyset\}$. Para cada $n\geq 0$, tome $a_n = g\left( A \cap \left( a - \frac{1}{n+1}, a + \frac{1}{n+1} \right) \right)$. Assim, temos uma função escolha para um intervalo em volta de a que vai se fechando.
Assim, $a_n$ é uma sequência de elementos de $A$ que satisfaz o que queremos. Vejamos, dado $\epsilon > 0$, tomemos $n_0 \in \omega$ tal que $\frac{1}{n_0 + 1} < \epsilon$, assim, para todo $n \in \omega\setminus n_0$, $a_n \in \left( a - \frac{1}{n + 1}, a + \frac{1}{n+1} \right) \subseteq (a - \epsilon, a + \epsilon)$. 

**Prop. (Equivalência em Continuidade de funções)**: São equivalentes:
- a) $f: \mathbb R \to \mathbb R$ é contínua em $a$;
- b) $\forall \epsilon > 0\exists \delta > 0\forall x\in dom f(|x - a| < \delta \to |f(x) - f(a)| < \epsilon)$;
- c) Para toda sequência $(a_n)_{n\in\omega}$ tal que $a_n \to a$, temos que a sequência dada por $(f(a_n))_{n\in \omega}$ converge para $f(a)$.
*Proof*: Sabemos que a) $\Longleftrightarrow$ b) pela definição de continuidade.
a) $\implies$ b) é simples, pois decorre do fato de que, como a sequência converge para $a$, existe um $n_\delta \in \omega$ tal que $\forall n \in \omega\setminus n_\delta$ vale que $|x - a| < \delta$ e, portanto, $|f(x_\delta) - f(a)| < \epsilon$, o que implica que $(f(a_n))_{n\in \omega}$ tende a $f(a)$. Para a volta, porém, precisaremos do Axioma da Escolha.
b) $\implies$ a) Vamos provar por contra-positiva. Suponha, então, que $\exists \epsilon > 0\forall \delta > 0 \exists x\in dom f(|x - a| < \delta \land |f(x) - f(a)|\geq \epsilon)$, podemos, então, para cada $k \in \omega$, escolher um $x_k$ tal que $|x_k - a| < \frac{1}{k}$, temos, assim, uma sequência convergente para $a$, mas, como $|f(x_k) - f(A)| \geq \epsilon$, $(f(x_k))_{k \in \omega}$ não tende a $f(a)$, o que termina nossa demonstração.

**Teorema**: Todo espaço vetorial tem base.
*Proof*: Seja $\mathcal C$ uma $\subseteq$-cadeia de subconjuntos L.I. de um espaço vetorial. Segue que $\bigcup \mathcal C$ é L.I., portanto segue que é maximal de $\mathcal C$. Pelo lema de Zorn, então, existe um conjunto maximal independente, este será base.

*Def.*: Interpretemos $\mathbb R$ como um $\mathbb Q$-espaço vetorial. Pelo teorema anterior, $\mathbb R$ tem base. Essas bases são chamada de Base de Hamel.
*Exemplo*: Seja $A$ o conjunto de todos conjuntos L.I. de números reais, sabemos que existe pelo Axioma da Potência. Vamos mostrar que $A$ possui elemento maximal e que todo $\subseteq$-maximal é uma base de Hemel.
Seja $A_0 \subseteq A$  uma $\subseteq$-cadeia, sabemos que $X_0 = \bigcup A_0$ é contém todos elementos de $A_0$, vejamos se está em $A$. Suponha, por absurdo, que não está. Então teríamos que:
$$
r_1x_1 + \dots + r_nx_n = 0
$$
com $r_i \in \mathbb Q \setminus \{0\}$ e $x_i \in X_0$ diferentes entre si. Sabemos que existem, para cada $i \in n + 1\setminus \{0\}$ $X_i$ tal que $x_i \in X_i$. Obtemos então um subconjunto $\{X_1,\dots,X_n\} \subseteq A_0$, assim, temos um maior elemento. Seja $X_i$ este maior elemento, segue que $x_1,\dots,x_n \in X_i$, assim, $X_i$ não é L.I., absurdo. Concluímos que toda cadeia tem elemento maximal.
Pelo Lema de Zorn, concluímos que $(A, \subseteq)$ tem elemento maximal $X$. Vamos provar que é uma base de Hamel.
Suponha que não seja, isto é, existe um $x \in \mathbb R$ que não pode ser escrito como combinação linear em $\mathbb Q$ de elementos de $X$. Pela maximalidade de $X$, segue que $X \subseteq X\cup\{x\}$ é L.D., assim, podemos escrever:
$$
0 = s_1x_1 + \dots + s_n x_n
$$
Mas, como $X$ é L.D., algum desses $x_i$ tem que ser $x$, podemos então isolá-lo e teríamos $x$ como uma combinação linear em $X$, absurdo. Logo, $X$ spans todo $\mathbb R$. 
Provemos, agora, que a combinação linear é única. Novamente, suponha por absurdo que não seja, então poderíamos escrever $x = r_1x_1 + \dots + r_nx_n = s_1x_1 + \dots + s_n x_n$. Teríamos:
$$
0 = (r_1 - s_1)x_1 + \dots + (r_n - s_n)x_n
$$
Segue de $X$ ser L.I. que todos $r_i - s_i = 0$, e, portanto, a combinação linear é única.