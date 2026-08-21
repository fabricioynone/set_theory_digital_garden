**Def.**: Sejam $\alpha$ e $\beta$ ordinais. Define-se soma ordinal de $\beta$ e $\alpha$, denotada por $\beta + \alpha$ recursivamente em $\alpha$, de modo que:
- $\beta + 0 = \beta$;
- $\beta + S(\alpha) = S(\beta + \alpha)$, se $\alpha$ é ordinal sucessor;
- $\beta + \alpha = \bigcup\{\beta + \xi : \xi < \alpha\}$, se $\alpha$ é ordinal limite.

Notemos que é uma extensão da dos naturais e não é comutativa. Por exemplo, $\omega + 1 \neq \omega$, mas $1 + \omega = \bigcup\{1 + n: n\in \omega\} = \omega$.

Para subtração de ordinais: 

**Lema**: $\alpha, \beta$ ordinais. Então $\alpha + \beta \geq \beta$.
*Dem.*: Indução Transifinita em $\beta$. Para $\beta = 0$, claramente $\alpha \geq 0$
Suponha que vale que $\alpha + \beta \geq \beta \in ON$. Então, $\alpha + S(\beta) = S(\alpha + \beta) \geq S(\beta) > \beta$.
Se $\beta$ é um ordinal limite e que $\alpha + \xi \geq \xi$ para todo $\xi < \beta$. Então, $\alpha + \beta = \bigcup\{\alpha + \xi : \xi < \beta\} \geq \bigcup\{\xi : \xi < \beta\} = \beta$.

**Lema**: Sejam $\alpha, \beta$ e $\gamma$ ordinais. Se $\beta < \gamma$, então, $\alpha + \beta < \alpha + \gamma$.
*Dem*.: Indução em $\gamma$. Para $\gamma = 0$, segue da hipótese.
Suponha que é verdadeira para um $\gamma \in ON$. Vejamos que é verdadeira para $\gamma + 1$. Se $\beta < \gamma + 1$, então $\beta \leq \gamma$. Temos:
- Se $\beta = \gamma$, então $\alpha + \beta = \alpha + \gamma$, logo, $\alpha + \beta < \alpha + (\gamma + 1)$;
- Se $\beta <\gamma$, então $\alpha + \beta < \alpha + \gamma$ pela HI, segue que $\alpha + \beta < \alpha + (\gamma + 1)$;
- Se $\gamma$ é um ordinal limite e $\beta < \gamma$, então $\beta \leq \xi$ para algum $\xi < \gamma$. Assim, $\alpha + \beta \leq \alpha + \xi < \alpha + S(\xi) \leq \alpha + \gamma$.

**Prop.**: Para quaisquer ordinais $\beta$ e $\alpha$, se $\beta \leq \alpha$, então existe um ordinal $\xi$ tal que $\beta + \xi = \alpha$. Tal ordinal é denotado $\alpha - \beta$.
*Dem.*: Seja $\alpha \in  ON$, suponha $\beta \leq \alpha$. Existe $\xi \in ON$ tal que $\beta +\xi > \alpha$, ($\alpha + 1$ seria um exemplo). Seja $\xi$ o menor ordinal onde isso acontece.
- Se $\xi = 0$, teríamos $\beta + \xi = \beta \leq \alpha$, assim $\xi$ não satisfaz $\beta + \xi = \alpha$. Absurdo.
- Se $\xi$ é ordinal limite, $\beta +\xi = \bigcup\{\beta + \gamma : \gamma < \xi\} \leq \alpha$, pela minimalidade de $\xi$. Absurdo.
- Se $\xi = S(\gamma)$, temos que $\beta + \gamma \leq \alpha$, pela minimalidade de $\xi$. Se $\beta + \alpha < \alpha$, temos que $\beta + \xi = \beta + S(\gamma) = S(\beta + \gamma) \leq \alpha$, absurdo. 
Para a unicidade, temos que, se $\xi'$ fosse outro ordinal tal que $\beta + \xi' = \alpha$, digamos, spg, que $\xi < \xi'$. Então, temos que $\alpha = \beta + \xi < \beta + \xi' = \alpha$, absurdo.

Veja um proposição que nos dá uma interpretação da soma de ordinais.

**Prop.**: Para quaisquer ordinais $\beta$ e $\alpha$, $\beta + \alpha$ é o tipo de ordem de $C_{\beta,\alpha} = \{0\}\times \beta\cup\{1\}\times \alpha$ dada pela ordenação lexicográfica.
*Dem.*: Indução em $\alpha$. Se $\alpha = 0$, de fato, $\{0\}\times \beta \cup \{1\}\times 0 = \{0\}\times \beta$ que é isomorfo a $\beta$. Suponha que vale para um $\alpha \in ON$. Temos que $C_{\beta,S(\alpha)} = C_{\beta,\alpha}\cup(1,S(\alpha))$ e $C_{\beta,\alpha}$ é um segmento inicial de $C_{\beta,S(\alpha)}$. Assium, seja $f: C_{\beta,\alpha} \to \beta + \alpha$ um isomorfismo, extendemos $f':C_{\beta,S(\alpha)}\to \beta + S(\alpha)$ par $f'((1,S(\alpha))) = \beta + \alpha$.
Suponha, agora, que $\alpha$ seja um ordinal limite e que seja verdade para todo $\xi < \alpha$. Então, $C_{\beta,\alpha} = \bigcup_{\xi < \alpha} C_{\beta,\xi}$, cada $C_{\beta,\xi}$ é isomorfo a um segmento inicial de $C_{\beta,\alpha}$. Seja $f|_{\xi}: C_{\beta,\xi}\to \beta + \xi$ o único isomorfismo entre as boas ordens. Pela unicidade dos isomorfismos (como vimos que são razoavelmente rígidos) para todo $\delta < \xi < \alpha$, $f_{\xi}|C_{\beta,\delta} = f_\delta$. Assim, $\bigcup_{\xi < \alpha}f_{\xi}: C_{\beta,\alpha} \to \bigcup_{\xi < \alpha}\beta + \xi = \beta + \alpha$ é um isomorfismo.

*Def.*: O produto de ordinais $\beta \cdot \alpha$ é definido recursivamente em $\alpha$ por:
- $\beta \cdot 0 = 0$
- $\beta \cdot S(\alpha) = \beta \cdot \alpha + \beta$
- $\beta \cdot \alpha = sup\{\beta\cdot\xi : \xi < \alpha\}$, se $\alpha$ é ordinal limite

Considere:
$$
G(\beta,s) = \begin{cases}
0, \text{ se } s = \emptyset \\
s(\alpha) + \beta, \text{ se } s \text{ é função }\land\exists\alpha\in ON (dom(s) = \alpha + 1) \\
\bigcup_{\xi < \alpha}s(\xi), \text{ se } s \text{ é função }\land \exists\alpha\in ON(dom(s) = \alpha) \text{ é limite} 
\end{cases}
$$
Notemos que o produto não é comutativo, uma vez que $2\omega = \omega$, mas $\omega \cdot 2 = \omega + \omega \neq \omega$.

*Def.*: $\beta^\alpha$ é definido recursivamente em $\alpha$ por:
- $\beta ^ 0 = 1$
- $\beta^{S(\alpha)} = \beta^\alpha \cdot \beta$
- $\beta^\alpha = sup\{\beta^\xi : \xi < \alpha\}$, se $\alpha$ é ordinal limite

Considere:
$$
G(\beta,s) = \begin{cases}
1, \text{ se } s = \emptyset \\
s(\alpha) \cdot \beta, \text{ se } s \text{ é função }\land\exists\alpha\in ON (dom(s) = \alpha + 1) \\
\bigcup_{\xi < \alpha}s(\xi), \text{ se } s \text{ é função }\land \exists\alpha\in ON(dom(s) = \alpha) \text{ é limite} 
\end{cases}
$$
