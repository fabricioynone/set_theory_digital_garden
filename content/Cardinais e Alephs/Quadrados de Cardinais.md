Vimos anteriormente que $\omega \times \omega$ é infinito enumerável, mas esse resultado não é particular apenas para $\aleph_0$, mas para todos cardinais infinitos. Isto é, para todo $\kappa$ cardinal infinito, vale que $\kappa \times \kappa \approx \kappa$.

Para isso, precisaremos:

## Ordem Canônica de $ON \times ON$
*Def*.: Um conjunto está em $ON\times ON$ se é um par ordenado de ordinais. 
Sejam $(\alpha,\beta)$ e $(\alpha',\beta')$ pares de ordinais, a ordem canônica de $ON\times ON$ é dada por
$$
\begin{align*}
(\alpha,\beta) \triangleleft (\alpha',\beta') \Longleftrightarrow &(\text{max}\{\alpha,\beta\} < \text{max}\{\alpha',\beta'\}\\
& \lor (\text{max}\{\alpha,\beta\} = \text{max}\{\alpha',\beta'\} \land \alpha < \alpha')\\
& \lor (\text{max}\{\alpha,\beta\} = \text{max}\{\alpha',\beta'\} \land \alpha = \alpha' \land \beta < \beta')
\end{align*}
$$

## A Ordem Canônica é Boa Ordem
**Lema**: Para cada cardinal $\alpha$, $\alpha \times \alpha$ é bem ordenado por $\triangleleft$ em $ON\times ON$, ou seja, para todos $(\alpha,\beta)$, $(\alpha',\beta')$ e $(\alpha'',\beta'')$ pares de ordinais, valem as seguintes propriedades:
- a) (Transitividade) Se $(\alpha, \beta) \triangleleft (\alpha',\beta')$ e $(\alpha',\beta') \triangleleft (\alpha'',\beta'')$, então $(\alpha, \beta) \triangleleft (\alpha'',\beta'')$
- b) (Não Reflexiva) $(\alpha, \beta) \not\triangleleft (\alpha',\beta')$
- c) (Tricotomia) $(\alpha,\beta) \triangleleft (\alpha',\beta') \lor (\alpha,\beta) = (\alpha',\beta') \lor (\alpha',\beta') \triangleleft (\alpha,\beta)$
- d) (Menor elemento) Se $X$ é um conjunto não vazio de pares de ordinais, então $X$ tem um $\triangleleft$-menor elemento.
*Proof*: a) Suponha que  $(\alpha, \beta) \triangleleft (\alpha',\beta')$ e $(\alpha',\beta') \triangleleft (\alpha'',\beta'')$, temos que $\text{max}\{\alpha,\beta\} \leq \text{max}\{\alpha',\beta'\} \leq \text{max}\{\alpha'',\beta''\}$, Se alguma for restrita vale o que queremos. Senão, temos que $\alpha \leq \alpha' \leq \alpha''$, novamente, se alguma for restrita, vale o que queremos. Senão, $\beta < \beta'<\beta''$ e vale o que queremos.
b) Segue da definição
c) Suponha que $(\alpha, \beta) \not\triangleleft (\alpha',\beta')$ e que $(\alpha', \beta') \not\triangleleft (\alpha,\beta)$, então, $\text{max}\{\alpha,\beta\} = \text{max}\{\alpha',\beta'\}$ e $\alpha = \alpha'$ e $\beta = \beta'$, seguindo a definição.
d) Seja $X$ um conjunto não vazio de ordinais, tomemos $X_0 = \{\text{max}\{\alpha,\beta\} : (\alpha, \beta)\in X\}$ é um conjunto de ordinais, então possui mínimo $\alpha_0$.
Definamos, agora, $Z = \{(\alpha,\beta)\in X : \alpha = \alpha_0\}$ e $Z_0 = \{\beta :(\alpha,\beta)\in Z\}$ é um conjunto de ordinais, então possui mínimo $\beta_0$.
Afirmamos que $(\alpha_0,\beta_0)$ é mínimo. De fato, seja $(\alpha,\beta)\in X$, temos que $\max\{\alpha_0,\beta_0\} \leq \max\{\alpha,\beta\}$. Se for estrito, segue que $(\alpha_0,\beta_0) \triangleleft (\alpha,\beta)$. Senão, $\alpha_0 \leq \alpha$,  e se for estrito segue o resultado, senão, $\beta_0 \leq \beta$ se for estrito, segue o resultado, senão, são iguais.

Se $(\alpha,\beta) \in ON\times ON$, denotamos $(\alpha,\beta)\downarrow = \{(\alpha',\beta') \in ON\times ON : (\alpha',\beta') \triangleleft (\alpha, \beta)\}$. Notemos que é de fato um conjunto pois $(\alpha, \beta) \subseteq \xi \times \xi$, para $\xi > \text{max}\{\alpha,\beta\}$.
Notemos, também, que $(\alpha, 0)\downarrow = (\alpha,\beta) \forall \alpha \in ON$

**Teorema**: Para cada cardinal infinito $\kappa$, $tp(\kappa\times\kappa, \triangleleft) = \kappa$.
*Proof*: Faremos por indução transfinita em $\alpha$. Primeiro, notemos que $\aleph_\alpha \preceq \aleph_\alpha\times\aleph_\alpha \, \forall \alpha\in ON$. Assim, temos que $tp(\aleph_\alpha \times \aleph_\alpha,\triangleleft)\geq |\aleph_\alpha\times\aleph_\alpha| = |\aleph_\alpha| =\aleph_\alpha$. Notemos que a primeira desigualdade vem do fato de que o ordinal é maior ou igual ao cardinal. Finalmente, mostremos, por indução transfinita, que $tp(\aleph_\alpha\times\aleph_\alpha,\triangleleft) \leq \aleph_\alpha$.
Suponha que vale para todo $\beta < \alpha$.
- Se $\alpha = 0$, suponha que $\gamma = tp(\omega\times\omega)$. Como $\omega\times\omega$ é infinito, sabemos que $\gamma \geq \omega$. Suponha que $\omega\times \omega \gt \omega$, como temos que $\omega \times \omega \cong \gamma$, existe $(m,n)\in \omega\times\omega$ tal que $(m,n) \cong \omega$, mas, $(m,n) \downarrow \subseteq \max\{m,n\} +1 \times\max\{m,n\} + 1$ que é finito absurdo. Assim, temos que $\gamma \not > \omega \implies \gamma = \omega$.
- Suponha que $\alpha > 0$. Suponha, por absurdo, que $tp(\aleph_\alpha\times\aleph_\alpha,\triangleleft) > \aleph_\alpha$. Seja $\xi = tp(\aleph_\alpha\times\aleph_\alpha,\triangleleft)$ e seja $f: \aleph_\alpha\times\aleph_\alpha \to \xi$ o único isomorfismo entre eles. Analogamente ao anterior, existem $\alpha_0, \beta_0 < \aleph_\alpha$ tal que $f(\alpha_0,\beta_0) = \aleph_\alpha$, assim, |$(\alpha_0,\beta_0)\downarrow$| = $\aleph_\alpha$. Se ambos são finitos, teríamos $|(\alpha_0,\beta_0)\downarrow| \leq |\max\{\alpha_0 + 1, \beta+0 + 1\}^2\downarrow|$ que é finito, absurdo. Logo, $\gamma = \max\{\alpha_0 + 1, \beta_0 +1\}$ é infinito de modo que $|(\alpha_0,\beta_0)| \leq |\gamma\times \gamma|$.
	Tomemos $\delta$ tal que $|\gamma| = \aleph_\delta$. Provemos que $\delta < \alpha$. Sabemos que $\gamma < \aleph_\alpha$, pois, como é infinito, é ordinal limite. Sabemos, também, que $|\gamma| \lt \aleph_\alpha \implies\aleph_\delta \lt\aleph_\alpha \implies \delta\lt\alpha$. Podemos, então, usar a hipótese de indução para escrever que $|\gamma\times\gamma| \leq |\aleph_\delta \times \aleph_\delta| = \aleph_\delta$. Temos então o absurdo:
$$
	\aleph_\alpha = |(\alpha_0,\beta_0)\downarrow| \leq |\gamma\times\gamma| \leq \aleph_\delta < \aleph_\alpha
	$$
**Corolário**: Qualquer conjuntos de pares de ordinais é bem ordenável e, para todo cardinal infinito $\kappa$, $|\kappa\times\kappa| = |\kappa|$
*Proof*: Como vimos na demonstração do teorema anterior, 
$$
|\kappa| = tp(\kappa\times\kappa,\triangleleft) \leq |\kappa \times \kappa| \leq |\kappa|
$$
