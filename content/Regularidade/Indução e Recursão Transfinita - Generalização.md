#### RECURSÃO TRANSFINITA
Antes de enunciar e provar o (meta)teorema da recursão transfinta generalizado para $R$ relações set-like bem fundadas, definemos e provemos algumas propriedades:

*Def.*: Seja $R$ uma relação definida set-like. Seja $G(p,s,a)$ um símbolo funcional ternário introduzido por definição.
Dados conjuntos $t,p,a$, escrevemos $Ap_G(t,p,a)$ e dizemos que $t$ é uma computação parcial em $a$ com parâmetro $p$ baseada em $G$ se, e somente se, valem:
- $t$ é função;
- $dom (t)$ é $R$-fechado
- $a\in dom(t)$
- $t(b) = G(p,t|_{pred_R(b)},b)$ para todo $b \in dom(t)$

**Lema**: Seja $R$ uma relação bem-fundada set-like e $G$ um símbolo funcional ternário introduzido por definição.
Se $t_1,\dots,t_n,a_1,a_2,p$ são tais que $Ap_G(t_1,p,a_1)$ e $Ap_G(t_2,p,a_2)$, então, $t_1$ e $t_2$ são compatíveis.
*Proof*: Suponha por absurdo que não, então consideremos
$$
X =  \{x\in domt_1\cap domt_2 : t_1(x)\neq t_2(x)\}
$$
é não-vazio pelo que assumimos, por $R$ ser bem fundado, tomemos $x$ $R-$minimal de $X$. Assim, temos que $\forall y(yRx)$, $y\in domt_1\cap domt_2$, pois ambos são $R$-fechados. Logo, $t_1(y) = t_2(y)$, pela minimalidade de $x$. Logo, $t_1|_{pred_R(x)} = t_2|_{pred_R(x)}$, logo, temos que 
$$
t_1(x) = G(p,t_1|_{pred_R(x)},x) = G(p,t_2|_{pred_R(x)}, x) = t_2(x)
$$
contradição.

Observemos que o lema anterior garante a unicidade de $t$.

**Corolário**: Considere $R$ uma relação set-like e bem fundada e $G$ um símbolo funcional ternário introduzido por definição.
Sejam $a$ e $p$ conjuntos. Se existe $t$ tal que $Ap_G(t,p,a)$, então existe um único $t'$ tal que $Ap_G(t',p,a)$ e $domt'= pred_R^*(a)\cup\{a\}$.
*Proof* : Provemos, primeiramente a existência. Tome $t'$ tal que $t'= t|_{pred_{R^*}(a)\cup\{a\}}$. Como $domt$ é $R$-fechado e $a \in domt$, temos $pred_R(a) \subseteq domt$. Como vimos anteriormente, $pred_{R^*}(a) \subseteq domt$. Obtemos, assim, que $pred_{R^*}(a)\cup\{a\} \subseteq domt$ e, então, podemos de fato pegar a restrição.
Mostremos, agora, que $t'$ é tal que $Ap_G(t',p,a)$. Sabemos que $domt'$ é $R$-fechado, pois, seja $b \in domt'$, se $b = a$, então, $pred_R(b) = pred_R(a) \subseteq pred_{R^*}(a) \subseteq domt'$, se $b \in pred_{R^*}(a)$, então vale que $pred_{R}(b) \subseteq pred_{R^*}(a)$.
Por último, tomemos novamente $b \in domt'$, então, $pred_R(b) \subseteq domt'$, logo, temos que $t'|_{pred_R(b)} = t|_{pred_R(b)}$, logo, $t'$ herda a equação recursiva que queremos em todos pontos em seu domínio.
Por fim, para a unicidade, sejam $t$' e $t''$ tais que $Ap_G(t',p,a)$ e $Ap_G(t'',p,a)$ e $domt'= domt'' = pred_{R^*}(a)\cup\{a\}$, então ambos são compatíveis e tem mesmo domínio.

**Lema**: Considere $R$ uma relação definida set-like e bem-fundada e $G$ um símbolo funcional ternário introduzido por definição. 
Para todo $a$ e $p$, existe um $t$ tal que $Ap_G(t,p,a)$.
*Proof*: Fixemos $p$. Vamos provar, por $R$-indução, que $\forall a\exists t(Ap_G(t,p,a))$. Dado, então, $a$, suponha que para todo $b\in pred_R(a)$ vale que $\exists t(Ap_G(t,p,b))$, usemos isso para provar que vale para $a$. 
Fixemos, para cada $b\in pred_R(a)$ um $t_b$ tal que $Ap_G(t_b,p,a)$ e usemos o corolário anterior para tomar $domt_c = pred_{R^*}(b)\cup\{b\}$. Como provamos que esse $t_c$ é único, podemos, pela Substituição, considerar a família $\{t_c : c \in pred_R(a)\}$.
Por um lema anterior, sabemos que são compatíveis, então, $t'= \bigcup_{b\in pred_R(a)}t_b$ é uma função. Além disso, 
$$
domt'= \bigcup_{b\in pred_R(a)}(pred_{R^*}(b)\cup\{b\}) = pred_{R^*}(a)
$$
Como $R$ é bem-fundada, $a\notin pred_{R^*}(a)$, pois, suponha que esteja, então teríamos um caminho $(a_0,\dots,a_n)$ de tamanho $n$ de $a$ para $a$, porém, o conjunto $\{a_0,\dots,a_n\}$ afirmaria que $aR^*a$, que é absurdo. 
Assim, $domt$' é $R$-fechado (pois $pred_{R^*}(a)$ é sempre $R$-fechado) e $a \notin domt'$. Tomemos, então:
$$
t = t'\cup\{a,G(p,t'|_{pred_R(a)},a)\}
$$
Então, temos $t$ funcão com domínio $domt = pred_{R^*}(a)\cup\{a\}$, de forma análoga a como provamos anteriormente, o domínio é $R$-fechado e $a\in domt$.
Chequemos a equação de recursão. 
- Para $b \in pred_{R^*}(a)$, sabemos que existe um $c \in pred_R(a)$ tal que $b\in pred_{R^*}(c)\cup \{c\}$, como $pred_R(b) \subseteq dom(t_c)$ e $t_c$ e $t$ coincidem, temos que
$$
t(b) = t_c(b) = G(p,t|_{pred_R(b)},b) = G(p,t_c|_{pred_R(b)},b) 
$$
- Para $a$, temos que 
 $$
t(a) = G(p,t|_{pred_R(a)},a)
$$
Encerrando a demonstração.

**(Meta?)Teorema (Esquema de Recursão Transifinita)**: Seja $R$ uma relação set-like e bem-fundada. Suponha que um símbolo funcional ternário $G(p,s,a)$ seja introduzido por definição. 
Então, vale
$$\forall a\forall p\exists !y\exists t(Ap_G(t,p,a)\land t(a) = y)$$
Seja $F^G$ o símbolo funcional binário introduzido por definição tal que 
$$
\forall a\forall p\forall y(F^G_p(a) = y \leftrightarrow (Ap_G(t,p,a) \land t(a) = y))
$$
Então, $\forall a\forall p(F^G_p(a) = G(p,F^G_p|_{pred_R(a)},a))$
*Proof*: Mostremos que, fixados $a$ e $p$, existe um único $y$ tal que 
$$
\exists t(Ap_G(t,p,a)\land t(a) = y)
$$
A existência segue do lema anteror. Provemos a unicidade: dados $t$ e $t$' tais que $Ap_G(t,p,a)$ e $Ap_G(t',p,a)$. Sabemos que são compatíveis e, por $a \in domt\cap domt'$, $t'(a) = t(a)$.
Novamente, fixemos $a$ e $p$ e tomemos $Ap_G(t,p,a)$. Então, para todo $b \in pred_R(a)$, temos $b \in domt$ e, portanto, $Ap_G(t,p,b)$, pela definição de $F^G$, segue que $t|_{pred_R(a)} =F^G_p|_{pred_R(a)}$. Assim, $F^G_p(a) = t(a) = G(p,t|_{pred_R(a)},a) = G(p,F^G_p|_{pred_R(a)},a)$.