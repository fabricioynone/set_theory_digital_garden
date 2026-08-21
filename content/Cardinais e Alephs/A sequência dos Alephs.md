Vimos que para todo cardinal $\kappa$, existe o menor cardinal maior que $\kappa$, o $\kappa^+$. Além disso, a união de cardinais é cardinal e $\omega$ é o menor cardinal infinito. 
Isso nos induz, intuitivamente, a definir uma sequência de cardinais
$$
\omega<\omega^+ < \omega^{++}<\dots
$$
E após os $\omega$ primeiros termos, seguimos com $\bigcup\{\omega, \omega^{+},\omega^{++},\dots\}$. A formalização disso nos leva a definição:

*Def.*: Define-se recursivamente, $\aleph_\alpha$ para cada ordinal $\alpha$ de modo que:
- a) $\aleph_0 = \omega$
- b) $\aleph_{\alpha + 1} = \aleph_\alpha^+$
- c) $\aleph_a = sup\{\aleph_\beta : \beta < \alpha\}$, para $\alpha$ ordinal limite.

**Lema**: Para cada ordinal $\alpha$, $\aleph_\alpha$ é cardinal e, para todo $\beta < \alpha$, $\aleph_\beta < \aleph_\alpha$.
*Dem.*: Indução transfinita. Suponha que é verdadeiro para todo $\beta < \alpha$.
- Se $\alpha = 0$, então $\aleph_0 = \omega$ é cardinal e o resto segue por vacuidade.
- Se $\alpha = \beta + 1$, então $\aleph_\alpha = \aleph_\beta^+$ que vimos que é um cardinal, Se $\gamma < \beta$, por hipótese de indução, temos que $\aleph_\gamma < \aleph_\beta < \aleph_\beta^+$. E sabemos que $\aleph_\beta < \aleph_\beta^+ = \aleph_\alpha$.
- Se $\alpha$ é ordinal limite, então $\aleph_\alpha = sup\{\aleph_\beta : \beta < \alpha\}$ é um cardinal, pois é união de cardinais. Seja $\gamma < \alpha$, como $\alpha$ é limite, $\gamma + 1< \alpha$, logo $\aleph_\gamma < \aleph_{\gamma + 1} < \aleph_\alpha$

Veremos que sequência dos $\aleph$ é a sequência de todos os ordinais finitos.

**Lema**: Para todo ordinal $\alpha$, $\aleph_\alpha \geq \alpha$.
*Dem.*: Indução transfinita. Suponha que seja verdadeira para todo $\beta < \alpha$. Se $\alpha = 0$, então $\aleph_\alpha = \aleph_0 \gt 0$.
Se $\alpha = \beta + 1$, então $\aleph_\alpha = \aleph_{\beta}^+ > \aleph_\beta \geq \beta$, assim, $\aleph_\alpha > \beta \implies \aleph_\alpha \geq \alpha = \beta + 1$.
Se $\alpha$ é ordinal limite, então $\aleph_\alpha = sup\{\aleph_\xi : \xi < \alpha\} \geq sup\{\xi : \xi < \alpha\} = \alpha$.

**Teorema**: Para cada cardinal infinito $\kappa$, existe um ordinal $\alpha$ tal que $\kappa = \aleph_\alpha$.
*Dem.*: Suponha que $\forall \alpha \in ON(\aleph_\alpha \neq \kappa)$, isto é, que não exista ordinal $\alpha$ tal que $\kappa = \aleph_\alpha$. Vamos provar, por indução transfinita, que, para todo ordinal $\alpha$, $\aleph_\alpha < \kappa$. Suponha que seja verdade para todo $\beta < \alpha$.
- Se $\alpha = 0$, $\aleph_\alpha = \omega \leq \kappa$, pois $\kappa$ é infinito.
- Se $\alpha = \beta +1$, $\aleph_\alpha = \aleph_\beta^+$, como vale que $\aleph_\beta < \kappa$ para todo $\beta < \alpha$ pela hipótese de indução, temos que $\aleph_\beta^+ \leq \kappa$, pelo que assumimos no início, $\aleph_\beta^+ < \kappa$.
- Se $\alpha$ é ordinal limite, $\aleph_\alpha = sup\{\aleph_\beta : \beta < \alpha\} \leq \kappa$. Pelo que assumimos no início, vale que $\aleph_\alpha < \kappa$.
Como vale para todos ordinais, em particular, vale para $\kappa +1$, isto é, vale que $\aleph_{\kappa + 1} < \kappa$, o que é absurdo, pois provamos que $\aleph_\kappa \geq \kappa$, portanto, teríamos que $\aleph_{\kappa + 1 } < \aleph_\kappa$, absurdo.

Outra notação para $\aleph_\alpha$ é $\omega_\alpha$. Nesse texto, $\aleph$ é o símbolo de cardinalidade e $\omega_\alpha$ é o ordinal.

*Def.*: Seja $\alpha$ ordinal. Define-se $\omega_\alpha$ o ordinal $\aleph_\alpha$.