Intuitivamente, rank mede a altura de um $x$ em relação a $R$. Elementos sem $R$-predecessores terão rank 0 e o rank de $x$ será definido estritamente maior do que o rank de cada predecessor de $x$.

*Def.*: Seja $R$ uma relação definida set-like bem-fundada. O rank de um conjunto $x$ com respeito a $R$, rank$_R(x)$ é definido recursivamente pela relação $R$ da seguinte forma:
$$
\text{rank}_R(x) = \bigcup S\{\text{rank}_R(y):yRx\}
$$
Tal que $S(u) = u\cup \{u\}$, a função sucessora.

Podemos formalizar a definição anterior usando o teorema da recursão visto em [[Indução e Recursão Transfinita - Generalização]] adicionando
$$
G(p,s,a) = \bigcup\{S(s(b)) : bRa \land b\in doms\}
$$
Temos, para todo $p$ e $a$,
$$
F^G_p(a) = G(p,F_p^G|_{pred_R(a)},a) = \bigcup\{S(F_p(b)): bRa\}
$$
Basta, assim, tomar $p$ qualquer (por exemplo, $p = \emptyset$) e temos rank$_R(a) = F^G_p(a)$.
 
**Lema**: Seja $R$ uma função definida set-like e bem-fundada, temos:
- i) Para todo $x$, rank$_R(x)$ é um ordinal;
- ii) Para todo $x$, rank$_R(x) = \sup\{\text{rank}_R(y) + 1 : yRx\}$
- iii) Para todos $x,y$, $yRx \implies \text{rank}_R(y) < \text{rank}_R(x)$
- iv) Para todos $x,y$, $yR^*x \implies \text{rank}_R(y) < \text{rank}_R(x)$
*Proof*: i) Segue por indução. Suponha que vale para todo $b$ tal que $bRa$ que rank$_R(b)$ é ordinal. Então, rank$_R(a) = \bigcup\{S(\text{rank}_R(b)):bRa\}$ é união de ordinais, portanto, é ordinal.
ii) segue de i) e da definição de supremo para ordinais.
iii) Se $yRx$, temos que rank$_R(y) + 1 \leq \text{rank}_R(x)$, pela anterior, segue que rank$_R(y) \lt \text{rank}_R(x)$.
iv) Se $yR^*x$, tomemos $(y, x_1,\dots,x)$ um $R$-caminho de tamanho $n$, pelo anterior, sabemos que $\text{rank}_R(y) < \text{rank}_R(x_1) <\dots< \text{rank}_R(x_{n-1}) < \text{rank}_R(x)$. 

*Def.*: Seja $R$ uma relação bem fundada e seja $A$ uma classe tal que $R_A$ é set-like e bem-fundada. Para $x\in A$, escrevemos rank$_{R,A} =$ rank$_{R_A}(x)$.

**Prop.**: Se $A$ é classe $R$-fechada e $R$ uma relação definida set-like e bem-fundada em $A$, então $R^*$ é set-like e bem-fundada em $A$.
*Proof*: Vimos que $R^*$ é set-like. Mostremos que é bem-fundada em $A$. Tomemos um subconjunto $X$ não vazio de $A$. Seja $\mathcal O = \{\text{rank}_{R,A}(x) : x\in X\}$, sabemos que $\mathcal O$ é um conjunto de ordinais, logo, possui um mínimo $\alpha = \min \mathcal O$. Tomemos, então, o $x$ tal que rank$_{R,A}(x) = \alpha$. Se $y\in X$ e $yR^*x$, como $A$ é $R$-fechada e $x \in A$, todo caminho de $y$ a $x$ está contido em $A$. Assim, $yR^*x$. Portanto, teríamos que $\text{rank}_R(y) < \text{rank}_R(x)) = \alpha = \min \mathcal O$, absurdo, pois pegamos $y \in X$.
Logo, construímos um elemento $R^*$-minimal de $X$, para $X \subseteq A$ não vazio arbitrário.

**Corolário**: Seja $R$ é relação definida set-like e bem-fundada, então $R^*$ é set-like e bem-fundada.
*Proof*: Tome $A = \mathbf V$

**Prop.**: Sejam $R$ e $S$ relações definidas tais que $R \subseteq S$. Se $S$ é set-like e bem-fundada, então, para todo $x$, $\text{rank}_R(x) \leq \text{rank}_S(x)$.
*Proof*: Provamos, anteriormente, que, nessas condições, $R$ herda ser set-like e bem fundada. Prossigamos, então, por $R$-indução. 
Suponha que para todo $y$ tal que $yRx$, $\text{rank}_R(y) \leq \text{rank}_S(y)$, sabemos, então, que:
$$
\text{rank}_R(x) = \sup\{\text{rank}_R(y) + 1 : yRx\} \leq \sup\{\text{rank}_S(y) + 1 : yRx\} = \text{rank}_S(x) 
$$

**Prop.**: Seja $R$ relação definida set-like e bem-fundada e $A$ uma classe. Se $x\in A$ tal que $pred_{R^*}(x) \subseteq A$, então $\text{rank}_{R,A}(x) = \text{rank}_{R}(x)$.
*Proof*: Como $R_A \subseteq R$, sabemos que $R_A$ é set-like e bem-fundada. Prossigamos por $R$-indução. Suponha que para todo $y\in A$ tal que $yRx$ vale que $pred_{R^*}(y) \subseteq A$, então $\text{rank}_{R,A}(y) = \text{rank}_{R}(y)$. Suponha que $x \in A$ e $pred_{R^*}(x) \subseteq A$. 
Dado $yRx$, temos que $pred_{R^*}(y) \subseteq pred_{R^*}(x) \subseteq A$, logo, $\text{rank}_{R,A}(y) = \text{rank}_{R}(y)$, temos, também, que $yR_Ax \Longleftrightarrow yRa$, pois $yRa \implies y\in pred_{R^*}(a) \subseteq A$. Logo, $\text{rank}_{R,A}(x) = \sup\{\text{rank}_{R}(y) + 1 yR_Ax\} = \sup\{\text{rank}_{R}(y) + 1 yRx\} = \text{rank}_R(x)$.

A próxima proposição irá concluir o capítulo mostrando que a operação $\text{rank}_R$ restrita à $pred_{R^*}(x)$ é sobrejetora em $\text{rank}_R(x)$ para todo $x$.

**Prop.**: Seja $R$ uma relação definida set-like e bem-fundada. Para todo $x$ e $\beta < \text{rank}_R(x)$ existe $y \in pred_R^*(x)$ tal que $\text{rank}_R(y) = \beta$.
*Proof*: Provemos por $R$-indução. Dado $x$ tal que vale a tese, para todo $yRx$. Se $\beta < \text{rank}_R(x)$, então sabemos que $\beta < \sup \{\text{rank}_R(y) + 1 : yRx\}$. Logo, existe $yRx$ tal que $\beta < \text{rank}_R(y) + 1 \implies \beta \leq \text{rank}_R(y)$. Se vale a igualdade, $y$ é o que queremos. 
Senão, pela segue pela hipótese de indução que existe um $z \in pred_R(y)$ tal que $\text{rank}_R(z) = \beta$, sabemos que $z\in pred_{R^*}(x)$.