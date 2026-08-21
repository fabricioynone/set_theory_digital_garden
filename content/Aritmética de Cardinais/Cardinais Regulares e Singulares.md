Seja $(\alpha_v : v\in \mathcal V)$ ser uma sequência transfinita de números ordinais de tamanho $\mathcal V$. Dizemos que é crescente se $\alpha_{v_1} < \alpha_{v_2}$ for all $v_1 < v_2 < \mathcal V$. Se $\mathcal V$ é um ordinal limite e $(\alpha_v : v\in \mathcal V)$ é crescente, nos definimos:
$$
\alpha = \lim_{v\to \mathcal V} \alpha_v = \sup\{\alpha_v : v\in \mathcal V\}
$$
E chamamos isso de limite da sequência.

*Def.*: Um cardinal infinito $\kappa$ é chamado de singular se existe uma sequência crescente transfinita $(\alpha_v : v < \mathcal V)$ de ordinais $\alpha_v < \kappa$ que o tamanho $\mathcal V$ é um ordinal limite menor que $\kappa$ e $\kappa = \lim_{v\in \mathcal V} \alpha_v$.
Um cardinal infinito que não é singular é chamado de regular.

Um subconjunto $X \subseteq \kappa$ é dito limitado se $\sup X < \kappa$ e ilimitado caso $\sup X = \kappa$.

**Teorema**: Seja $\kappa$ um cardinal regular.
- a) Se $X \subseteq \kappa$ é tal que $|X| < \kappa$, então $X$ é limitado. Assim, todo subconjunto ilimitado de $\kappa$ tem cardinalidade $\kappa$.
- b) Se $\lambda < \kappa$ e $f: \lambda \to \kappa$, então $f[\lambda]$ é limitado.
*Proof*: a) Se $X$ tem um maior elemento $\alpha$, então $\sup X = \alpha < \kappa$, pois $\kappa \not\in \kappa$. Asumamos que a ordem seja um ordinal limite, então, seja $(\alpha_v : v < \mathcal V)$ uma enumeração crescente de $X$. Como $|\mathcal V| = |X| < \kappa$, temos que $\mathcal V < \kappa$ e, por $\kappa$ ser regular, segue que $\sup X < \kappa$.
b) Como $|f[\lambda]| \leq \lambda < \kappa$, segue de a).

*Exemplos*: de cardinais singulares.
$\aleph_\omega = \lim_{n\to \omega}\aleph_n$, onde $\omega < \aleph_\omega$ e $\aleph_n < \aleph_\omega$ para todo $n \in \omega$. Similarmente, os cardinais $\aleph_{\omega + \omega}$ e $\aleph_{\omega \cdot \omega}$ são singulares. Por outro lado, $\aleph_0$ é regular.

**Lema**: Um cardinal infinito $\kappa$ é singular se e somente se é a soma de cardinais menores. Isto é, $\kappa = \sum_{i\in I} \alpha_i$ tal que $\alpha_i < \kappa$ e $|I| < \kappa$.
*Proof*: Se $\kappa$ é singular, então existe uma sequencia transfinita tal que $\kappa = \lim_{v\in \mathcal V}\alpha_v$ onde $\alpha_v < \kappa$ e $\mathcal V < \kappa$. Como todo o ordinal é conjunto de ordinais menores, podemos escrever
$$
\kappa = \bigcup_{v\in \mathcal V} \alpha_v = \bigcup_{v\in \mathcal V} \left(\alpha_v - \bigcup_{\xi < v}\alpha_\xi\right)
$$
Se tomarmos $A_v = \alpha_v - \bigcup_{\xi < v}\alpha_\xi$, então $(A_v : v\in \mathcal V)$ é uma sequência de cardinais menores que $\kappa$ de conjuntos de cardinalidade $k_v = |A_v| = |\alpha_v - \bigcup_{\xi < v}\alpha_\xi| \leq \alpha_v < \kappa$, como $A_v$ são mutualmente disjuntos, isso mostra que $\kappa = \sum_{v\in \mathcal V}\kappa_v$.
Reciprocamente, assuma que $\sum_{\alpha<\lambda} \kappa_\alpha = \kappa$ onde $\lambda$, $\kappa_\alpha < \kappa$. Temos $\sum_{\alpha < \lambda}\kappa_\alpha = \lambda \sup_{\alpha < \lambda}\kappa_\alpha$, logo, temos que $\kappa = \lambda \sup_{\alpha < \lambda}\kappa_\alpha$, como temos que $\lambda < \kappa$, concluímos que $\kappa = \sup_{\alpha < \lambda}\kappa_\alpha$, assim, a sequência $(\kappa_\alpha : \alpha < \kappa)$ tem supremo $\kappa$ e podemos achar por recursão trasnfinita uma subsequência (permutação ?) crescente. Claramente, o tamanho da subsequência é menor que $\lambda$.

**Teorema**: Todo cardinal sucessor $\aleph_{\alpha + 1}$ é um cardinal regular.
*Proof*: Senão, $\aleph_{\alpha + 1}$ seria a soma de um número menor de cardinais menores, isto é
$$
\aleph_{\alpha + 1} = \sum_{i\in I} \kappa_i
$$
Onde $|I| = \aleph_{\alpha + 1}$ e $\kappa_i < \aleph_{\alpha + 1}$ para todo $i \in I$. Assim, $|I| \leq \aleph_\alpha$ e $\kappa_i \leq \aleph_\alpha$ e temos:
$$
\aleph_{\alpha + 1} = \sum \kappa_i \leq \sum \aleph_\alpha = \aleph_\alpha \cdot |I| \leq \aleph_\alpha\cdot \aleph_\alpha = \aleph_\alpha
$$
Absurdo, portanto, $\aleph_{\alpha + 1}$ é regular.

Assim, todo cardinal singular é um cardinal limite.

**Lema**: Existem cardinais singulares arbitrariamente grandes.
*Proof*: Seja $\aleph_\alpha$ um cardinal arbitrário, consideremos a sequência $\aleph_\alpha, \aleph_{\alpha+1},\dots$, para $n\in \omega$, assim, temos:
$$
\lim_{n\to \omega} \aleph_{\alpha + n } = \aleph_{\alpha + \omega}
$$
e, assim, temos que $\aleph_{\alpha +\omega}$ é um cardinal singular maior que $\aleph_\alpha$.

Todos os cardinais limites incontável que vimos até agora são singulares. Será que existem incontáveis cardinais limites regulares?
Suponha que tenha, então, como $\alpha$ e o ordinal limite, 
$$
\aleph_\alpha = \lim_{\beta \to \alpha} \aleph_\beta
$$
Isto é, $\aleph_\alpha$ é o limite de uma sequência crescente de tamanho $\beta$. Como $\aleph_\alpha$ é regular, temos que $\alpha \geq \aleph_\alpha$, o que junto com $\alpha \leq \aleph_\alpha$ nos dá
$$
\aleph_\alpha = \alpha
$$
Isso já sugere que $\aleph_\alpha$ é grande. Apesar de parecer uma condição forte, veremos que não é tão poderosa assim.

**Lema**: Existem cardinais singulares arbitrariamente grandes $\aleph_\alpha$ tais que $\aleph_\alpha = \alpha$.
*Proof*: Seja $\aleph_\gamma$ um cardinal arbitrário. Considere a seguinte sequência: $\alpha_0 = \omega_\gamma, \alpha_1 = \omega_{\alpha_0} = \omega_{\omega_\gamma}\dots$ para todo $n\in \omega$. Seja $\alpha = \lim_{n\to \omega} \alpha_n$. É claro que a sequência $(\aleph_{\alpha_n}: n\in \omega)$ tem limite $\aleph_\alpha$. Mas, então, teremos:
$$
\aleph_\alpha = \lim_{n\to \omega} \aleph_{\alpha_n} = \lim_{n\to \omega} \alpha_{n+1} = \alpha
$$
Como $\aleph_\alpha$ é o limite de uma sequência de cardinais menores de tamanho $\omega$, é singular.

Um cardinal incontável que é cardinal limite e regular é chamado de *inacessível*, frequentemente chamado de *fracamente inacessível*, para distinguir de um outro tipo com propriedades mais fortes. Não se pode provar a existência de cardinais inacessíveis usando apenas a ZFC.

*Def.*: Se $\alpha$ é um ordinal limite, então a cofinalidade de $\alpha$, denotada $cf(\alpha)$, é o menor ordinal $\mathcal V$ tal que $\alpha$ é o limite de uma sequência crescente de ordinais de tamanho $\mathcal V$.

Notemos que $cf(\alpha)$ é um ordinal limite e que $cf(\alpha) \leq \alpha$. Assim, $\aleph_\alpha$ é singular se $cf(\omega_\alpha) < \omega_\alpha$ e regular se $cf(\omega_\alpha) = \omega_\alpha$.

**Lema**: Se um ordinal limite $\alpha$ não é um cardinal, então $cf(\alpha) < \alpha$.
*Proof*: Seja $\alpha$ um ordinal limite tal que não seja um cardinal. Se tomarmos $\kappa = |\alpha|$, sabemos que existe uma bijeção de $\kappa$ em $\alpha$, isto é, uma sequência $(\aleph_v : v \in \mathcal V)$ de tamanho $\kappa$ tal que $\{\alpha_v : v < \mathcal V\} = \alpha$, podemos então, achar uma subsequência crescente e tem limite $\alpha$. Como o tamanho da subsequência é no máximo $\kappa$ e $\kappa = |\alpha| < \alpha$, pois $\alpha$ não é cardinal, concluímos que $cf(\alpha) < \alpha$.

**Corolário**: Para todos ordinais limite $\alpha$, $cf(\alpha) = \alpha \Longleftrightarrow \alpha$ é regular.

**Lema**: Para todo ordinal limite $\alpha$, $cf(cf(\alpha)) = cf(\alpha)$.
*Proof*: Seja $\mathcal V = cf(\alpha)$, $\mathcal V$ é um ordinal limite e $cf(\mathcal V) \leq \mathcal V$. Resta mostrar que $cf(\mathcal V) \not< \mathcal V$. Suponha que $\gamma = cf(\mathcal V) < \mathcal V$, então existe uma sequência crescente de ordinais $(\mathcal V_\xi : \xi < \gamma)$ de tamanho $\gamma$ e $\lim_{\xi \to \gamma} \alpha_{\gamma_\xi} = \alpha$. Mas $\gamma < \mathcal V$, contradição.

**Corolário**: Para todo limite ordinal $\alpha$, $cf(\alpha)$ é um cardinal regular.
