Vimos que, para todo conjunto finito, existe um natural $n\in \omega$ tal que $A \approx n$. Veremos que temos representantes canônicos também para os infinitos bem ordenáveis, isto é, os conjuntos que podem ser contatos até o fim usando ordinais *(talvez o mesmo esquema que fazemos na demonstração de que todo conjunto bem ordenado é representado por um cardinal)*. Usando o axioma da escolha, veremos que todos conjuntos são bem ordenáveis.

**Lema**: Seja $A$ um conjunto bem ordenado, então existe $\alpha\in ON$ tal que $A \approx \alpha$.
*Dem.*: Seja $<$ a boa ordem de $A$. Existe um único ordinal $\alpha$ tal que $(A,<)$ é isomorfo a $\alpha$, pelo teorema que vimos anteriormente. Como isomorfismo é bijeção, segue que $\alpha \approx A$.

Ao contrário de ordinais finitos, um conjunto infinito não está em bijeção apenas com um ordinal. Apesar de, de início, parecer contraditório com a noção que temos de que o isomorfismo é único, lembre-se que uma bijeção não precisa preservar ordem.

*Exemplos*: $\omega + 1 = \omega \cup \{\omega\}$ é enumerável pois é união de dois conjuntos enumeráveis. Analogamente, $\omega + \omega = \omega \cup \{\omega  + n : n \in \omega\}$ também é enumerável.

Assim, segue que todos conjuntos enumeráveis são isomorfos a $\omega, \omega + 1,\dots, \omega + \omega$ e muitos outros. Para garantir a unicidade, definimos a cardinalidade como o menor deles. Vejamos:

*Def.*: Seja $A$ um conjunto bem ordenável. A cardinalidade de $A$, ou o número de elementos de $A$, é o menor ordinal que está em bijeção com $\alpha$. O cardinal de $A$ é denotado $|A|$.

**Lema**: Seja $\alpha$ um ordinal. Então $\alpha$ é cardinalidade de um conjunto bem ordenável se, e somente se, não existe $\beta < \alpha$ tal que $\alpha$ esteja em bijeção com $\beta$.
*Dem.*: Suponha que não existe $\beta < \alpha$ tal que $\alpha$ esteja em bijeção com $\beta$. Assim, $\alpha$ é bem ordenável e não existe $\beta < \alpha$ em bijeção com $\beta$, assim, pela definição anterior, $|\alpha| = \alpha$.
Reciprocamente, suponha que $\alpha$ é cardinalidade de algum $A$ conjunto bem ordenável. Por definição, $\alpha$ é o menor ordinal que está bem bijeção com $A$, assim, não existe $\beta < \alpha$ em bijeção com $\alpha$, pois estaria em bijeção com $A$ e violaria e minimalidade.

*Def.*: Um cardinal é um ordinal $\kappa$ que satisfaz alguma (e, portanto, todas) as seguintes condições equivalentes:
- (i) $\kappa$ é cardinalidade de um conjunto ordenável;
- (ii) não existe $\beta < \kappa$ tal que $\beta \approx \kappa$.

*Exemplos*: Todo natural é cardinal. De fato, se $m <n \implies m \subsetneq n \implies m\not\approx n$ )(comentar que talvez nao precisasse do conter por causa dum lema)
$\omega$ é cardinal, pois, como $\omega$ é infinito, para todo $n \in \omega$, $n \not\approx \omega$.
$\omega + \omega$ não é um cardinal, pois $\omega + \omega \approx \omega$.

**Lema**: Seja $\alpha$ um ordinal. Então $\alpha$ é um cardinal se, e somente se, para todo $\beta < \alpha$, não existe injeção de $\beta$ em $\alpha$.
*Dem.*: Dado $\beta < \alpha$, temos que $\beta \subseteq \alpha$ e, portanto, a identidade é uma injeção de $\beta$ em $\alpha$, logo, $\beta \preceq \alpha$. Pelo Teorema de Cantor-Shroder-Berstain, temos que $\alpha \approx \beta$ se, e somente se, $\alpha \preceq \beta$.
Assim, existe um $\beta < \alpha$ tal que $\alpha \approx \beta$ se, e somente se, $\beta < \alpha$ tal que $\alpha \preceq \beta$. Provado pela contra-positiva.

**Lema**: Sejam $A$ e $B$ bem ordenáveis. Então:
- a) $|A| = |B|$ sse $A \approx B$
- b) $|A| \leq |B|$ sse $A\preceq B$
- c) |A| < |B| sse $A \prec B$
- d) ||A|| = |A|
*Dem.*: a) se $|A| = |B|$, então, $A \approx |A| = |B| \approx B$. Se $A \approx B$, então para todo $\alpha$ cardinal, temos que $A \approx \alpha$ sse $B \approx \alpha$, assim, segue da transitividade e minimalidade "unicidade "do cardinal, que $A \approx B$.
b) Se $|A| \leq |B|$, então $A\preceq |A| \leq |B|\preceq B$. Pela contra-positva, suponha que $|B| < |A|$, como $A$ é cardinal, $|A| \not\preceq |B|$ pelo lema anterior.
c) consequência direta de a) e b)
d) como $|A|$ é cardinal, $|A|$ não bijeta com nenhum outro ordinal menor que ele, logo, $|A| = ||A||$, análogo à prova do segundo lema.

Note que ainda não provamos a existência de ordinais não enumeráveis ou de boas ordens não enumeráveis. Todos os cardinais que temos até agora são $n \in \omega$ e $\omega$. Utilizaremos o axioma da potência para construir mais cardinais.

**Prop.**: Para todo conjunto $A$, existe um ordinal $\alpha$ tal que $A \not\preceq \alpha$.
*Dem.*: Considere $Z = \{(B,R)\in P(A)\times P(A\times A): R \text{ é boa ordem sobre }B\}$. Pelo axioma da substituição, considere o conjunto $\alpha = \{tp(B,R): (B,R)\in Z\}$. Provemos que é ordinal. Como $\alpha$ é um conjunto de ordinais, basta mostrar que é transitivo. Tomemos $\beta \in \alpha$ e $\gamma \in \beta$ e seja $(B,R)$ tal que $\beta = tp(B,R)$. Tomemos o único isomorfismo $\phi: \beta \to B$ que preserva a ordem $R$ e consideremos $\phi|_{\gamma}: \gamma \to \{b\in B : bR\phi(\gamma)\}$ é um isomorfismo. Assim, concluímos que $\gamma \in \alpha$. 
Concluímos, portanto, que $\alpha$ é ordinal. Provemos que não injeta com $A$. Suponha que exista $f: \alpha \to A$ injetora. Seja $B = f[\alpha]$ e seja $R$ a relação dada por $f(\gamma)Rf(\xi)$ sse $\gamma R \xi$, então $f: (\alpha, <)\to (B,R)$ é um isomorfismo, mas $tp(B,R) = \alpha \implies \alpha \in \alpha$, absurdo.

*Def.*: O número de Hartogs de um conjunto $A$, denotado por $h(A)$ é o menor ordinal $\alpha$ tal que $\alpha$ que não injeta em $A$. 

**Lema**: Seja $A$ um conjunto. Então $h(A)$ é um cardinal.
*Dem.*: Suponha $h(A)$ não é cardinal, então existe $\beta\in ON$ tal que $\beta < h(A)$ e que $\beta \approx h(A)$, pela definição, temos que $\beta \preceq A$, assim, $h(A) \preceq A$, absurdo.

**Lema**: Seja $\alpha$ um ordinal. Então $h(\alpha)$ é o menor ordinal $\kappa$ tal que $\alpha < \kappa$.
*Dem.*: Como $h(\alpha) \not\preceq \alpha$, temos que $h(\alpha) \neq \alpha$. Como ambos são ordinais comparáveis, sabemos que $h(\alpha) > \alpha$. 
Seja $\kappa$ o menor ordinal tal que $\alpha < \kappa$. Como $\kappa$ não injeta em $\alpha$, temos que $h(\alpha) \leq \kappa$.

*Def.*: Dado um ordinal $\alpha$, o número de Hartogs de $\alpha$ é denominado $\alpha^+$

**Lema**: Seja $A$ uma coleção de cardinais. Então, $\bigcup A$ é um cardinal.
*Dem.*: Sabemos que $\bigcup A$ é uma união de ordinais, portanto, é um ordinal. Consideremos $\alpha < \bigcup A$. Seja $\kappa \in A$ tal que $\beta < \kappa$, como $\kappa$ é um cardinal, não injeta com $\beta$, assim, $\beta \not\preceq \bigcup A$.

**Lema**: Se $\kappa$ é um cardinal infinito, então $\kappa$ é ordinal limite.
*Dem.*: Se $\kappa$ é um cardinal, por ser infinito, $\kappa \neq 0$. Suponha que $\exists \alpha \in ON (S(\alpha) = \kappa$. Como $\kappa = \alpha \cup \{\alpha\}$ é infinito, $\alpha$ também é. Assim, $\omega \subseteq \alpha$ e podemos definir
$$
f(\xi) = \begin{cases}
\xi + 1,\text{ se } \xi < \omega \\
\xi, \text{ se } \omega \leq \xi < \alpha \\
0, \text{ se } \xi = \alpha
\end{cases}
$$
Fácil ver que é injetora. Assim, concluímos que existe $\alpha < \kappa$ tal que $\alpha \preceq \kappa$, absurdo, pois $\kappa$ é cardinal.