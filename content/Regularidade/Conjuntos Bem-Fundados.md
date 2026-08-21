Vamos introduzir a classe de conjuntos bem-fundados. Para isso, definamos:

*Def.*: Seja $x$ um conjunto, o fecho transitivo de $x$ é o conjunto $trcl(x) = pred_{\in^*}(x)$ em que $\in^*$ é a transitivização de $\in$.

Notemos que a definição faz sentido, pois $\in$ é set-like e, portanto, $\in^*$ também é set-like. Note que classes transitivas são sinônimos de classes fechadas.

**Lema**: Para quaisquer $x$ e $y$, temos:
- a) $trcl(x)$ é transitivo;
- b) $x \subseteq trcl(x)$
- c) Se $T$ é classe transitiva e $x \subseteq T$, então $trcl(x) \subseteq T$;
- d) Se $T$ é classe transitiva e $x \in T$, então $trcl(x) \subseteq T$;
- e) Se $y \subseteq x$, então $trcl(y) \subseteq trcl(x)$;
- f) $trcl(x) = \bigcup_{y\in x} (trcl(y)\cup\{y\})$
*Proof*: Caso particular de um lema feito anteriormente, mais especificamente, em [[Relações Bem Fundadas]].

*Def.*: Um conjunto $x$ é bem-fundado se, e somente se, $\in$ é bem-fundado em $trcl(x)$. A classe dos conjuntos bem-fundados é denotado por $WF$.

**Lema**: Um conjunto $x$ é bem-fundado se, e somente se, $\in$ é bem-fundado em alguma classe transitiva $t$ tal que $x \subseteq t$. *(Se pá que teve typo na notação)*
*Proof*: Suponha $x$ bem fundado, então $\in$ é bem fundado em $trcl(x)$, que é transitiva e contém $x$ ($t = x$).
Reciprocamente, suponha que $\in$ é bem-fundado em alguma classe transitiva $t$ que contém $x$, pelo lema anterior, vimos que $trcl(x) \subseteq t$, logo, $trcl(x)$ é bem-fundado tomando a restrição de $\in$ para $trcl(x)$.

**Lema**: Se $x$ é bem-fundado, então, $x\notin^* x$.
*Proof*: Suponha que $x\in^* x$. Então, $x \in trcl(x)$ e temos que $\{x\} \subseteq trcl(x)$, porém, $\{x\}$ não tem $\in^*$-minimal, pois existe $y\in \{x\}$ tal que $y\in^* x$, o que é absurdo com o fato de $trcl(x)$ ser bem-fundado.

**Lema**: Seja $x$ um conjunto. Então, $x$ é bem-fundado se, e somente se, $\in$ é bem-fundado em $trcl(x)\cup\{x\}$.
*Proof*: Suponha que $\in$ é bem-fundado em $trcl(x)\cup\{x\}$, segue que $\in$ é bem fundado em $trcl(x) \subseteq trcl(x)\cup\{x\}$, isto é, que $x$ é bem fundado.
Suponha $x$ bem fundado, então $\in$ é bem-fundado em $trcl(x)$. Vamos mostrar agora que todo subconjunto de $trcl(x)\cup\{x\}$ tem $\in$-minimal. Seja um $X \subseteq trcl(x)\cup\{x\}$:
- i) se $x \notin X$, então $X \subseteq trcl(x)$ e segue por hipótese que tem minimal.
- ii) se $X = \{x\}$, segue que $x$ é $\in$-minimal do lema anterior.
- iii) Se $x \in X$, definamos $Y = X\setminus \{x\}$, sabemos que $Y \subseteq trcl(x)$, logo, possui um $y$ que é $\in$-minimal. Sabemos que para todo $z\in Y(z\notin y)$ e, $x \notin z$, pois, se estivesse, teríamos $x\in y \in^* x \implies x \in^* x$, absurdo pelo lema anterior.

Definamos, agora, o rank de um conjunto bem fundado. Para fins de abreviação, denotaremos por $rk(x)$.

*Def.*: Se $x\in WF$, então $rk(x) = rk_{\in, trcl(x)\cup\{x\}}(x)$

**Prop.**: Se $T$ é classe transitiva tal que $\in$ é bem-fundada em $T$, então:
- a) $T \subseteq WF$;
- b) $rk_{\in,T}(x) = rk(x) \forall x\in T$
*Proof*: a) Como $T$ é transitivo, sabemos que (pelo primeiro lema dessas notas) para todo $x\in T (trcl(x)\cup\{x\} \subseteq T)$, sabemos também que $T$ é bem-fundado, logo, $\forall x\in T (trcl(x)\cup\{x\}\text{ é bem-fundado})$, assim, concluímos que $T \subseteq WF$.
b) Usando novamente que $trcl(x)\cup\{x\} = t$, temos que $(\in_T)_t = \in_t$. Além disso, 
$$
pred_{(\in_t)^*}(x) \subseteq pred_{\in^*}(x) \subseteq trcl(x)\cup\{x\}
$$
Como $\in$ é definida set-like e bem fundada, segue que $rk(x) = rk_{\in,T}(x) = rk_{\in_T}(x) = rk_{\in,T}(x)$.

**Prop.**: $WF$ é classe transitiva e $\in$ é bem-fundada em $WF$.
*Proof*: Seja $x\in WF$ e $y\in x$, temos que $y\in x \implies y \in^* x \implies y\in pred_{\in^*}(x) = trcl(x)$ e, então, $trcl(y) \subseteq trcl(x)$, logo $\in_{trcl(y)} \subseteq \in_{trcl(x)}$ e, portanto, $y \in WF$, pois concluímos que $\in$ é bem fundado em $trcl(y)$. *(Observar diferença na demonstração)*
Seja $X \subseteq WF$ não-vazio, consideremos usando o Axioma da Substituição o conjunto $\{rk(z) : z\in X\}$, sabemos que é um conjunto de ordinais e portanto, podemos pegar um $x \in X$ tal que $rk(x)$ é o menor rank de $X$. Provemos que é o menor elemento de $X$.
Se $y\in X$ pela prop. anterior, temos
$$
rk(y) = rk_{\in,trcl(y)\cup\{y\}}(y) < rk_{\in,trcl(x)\cup\{x\}}(x) = rk(x) 
$$
logo, $y \notin X$

Note que concluímos que para todo $x \in WF$, $rk(x) = rk_{\in,WF}(x)$.

**Corolário**: $x\in WF$, então $rk(x) = \sup\{rk(y) + 1: y\in x\}$.
*Proof*: $x\in WF$. 
$$
rk(x) = rk_{\in,WF}(x) = \sup\{rk(y) + 1: y\in_{WF} x\} = \sup\{rk(y) + 1: y\in x\}
$$

**Corolário**: Sejam $x, y\in WF$ tais que $x\in^* y$, então $rk(x) < rk(y)$.
*Proof*: $WF$ transitiva $\implies WF\in$-fechada, assim $(\in_{WF})^* = (\in^*)_{WF}$ e temos, para $x,y\in WF$, $x\in^* y \implies x (\in_{WF})^* y \implies rk_{\in,WF}(x) < rk_{\in,WF}(y) \implies rkx < rky$.

**Corolário**: $x,y \in WF$ e $x \subseteq y$, então $rk(x) \leq rk(y)$.
*Proof*: $rk(x) = \sup\{rk(z):z\in x\} < \sup\{rk(z):z\in y\} = rk(y)$.

**Corolário**: Para todo $x$, $x \in WF \Longleftrightarrow x\subseteq WF$.
*Proof*: Suponha que $x\in WF$, como $WF$ é transitivo, sabemos que $x \subseteq WF$. Reciprocamente, suponha $x \subseteq WF$, então, $trcl(x) \subseteq WF$, pois $WF$ é transitivo. Como $WF$ é bem-fundada, $\in$ é bem-fundada em $trcl(x)$, logo $x \in WF$.

**Lema**: Para todo $\alpha \in ON$, $\alpha$ é bem-fundado e $rk(\alpha) = \alpha$.
*Proof*: Indução transfinita. Suponha que para todo $\beta < \alpha (\beta \in WF)$. Assim, temos que $\alpha =\{ \beta : \beta < \alpha\} \subseteq WF$, portanto, $\alpha \in WF$.
$rk(\alpha) = \sup\{rk(\beta) + 1 : \beta \in \alpha\} = \sup\{rk(\beta) + 1 : \beta < \alpha\}= \alpha$, pois $\alpha$ é o menor majorante. Considere $A = \{\beta : \beta < \alpha\}$, sabemos que se $\xi < \alpha \implies \xi + 1 \in A$, logo $\xi$ não é majorante de $A$, pois $\xi + 1 \leq \alpha$.

Concluímos, então, que $ON \subseteq WF$.

**Corolário**: Sejam $x,y \in WF$. Então:
- a) $rk(\{x,y\}) = \max\{rk(x),rk(y)\} + 1$;
- b) $rk(\langle x,y\rangle) = \max\{rk(x),rk(y)\} + 2$;
- c) $trcl(x) \in WF$ e $rk(trcl(x)) = rk(x)$;
- d) $\bigcup x\in WF$ e $rk\left(\bigcup x\right) \leq rk(x)$;
- e) $x\cup y$ é bem-fundado e $rk\left(x\cup y\right) = \max\{rk(x),rk(y)\}$;
- f) Se existe $\mathcal P(x)$, então $\mathcal P(x) \in WF$ e $rk\left(\mathcal P(x)\right) = rk(x) + 1$.
*Proof*: a) $\{x,y\} \subseteq WF \implies \{x,y\} \in WF$. Ademais:
$$
rk(\{x,y\}) = \sup\{rk(z) + 1: z\in \{x,y\}\} = \max\{rkx + 1,rky + 1\} = \max\{rkx,rky\} + 1
$$
b) $\langle x,y\rangle = \{\{x\},\{x,y\}\}$, logo, segue do que mostramos na prova de a) que $\langle x,y \rangle \in WF$, segue, também por a), que:
$$
\begin{align}
rk\langle x,y \rangle = \sup \{rkz + 1: z\in \langle x,y \rangle\} &= \max\{rk\{x\} + 1,rk\{x,y\} + 1\}\\
&= \max\{rk\{x\} + 1, \max \{rkx + 1, rk y + 1\} + 1 \}\\
&= \max\{rkx,rky\} + 2
\end{align}
$$
c) $trcl(x) \subseteq WF \implies trcl(x) \in WF$. Seja $y \in trcl(x)$, sabemos que $y \in WF$ e que $y\in^* x$, logo, $rky < rkx \implies rk(trcl(x)) \leq rk(x)$. Por outro lado, $x \subseteq trcl(x)$, logo, $rk(x) \subseteq rk(tlcr(x)$, segue a igualdade.
d) $\bigcup x = \{y: y\in x\} \implies \bigcup x \subseteq trcl(x) \subseteq WF$. Logo, concluímos que $\bigcup x \in WF$. Além disso, segue que $rk\left(\bigcup x\right) \leq rk(trcl(x)) = rkx$.
e) Caso particular do anterior para mostrar que está em $WF$. Para o rank:
$$
\begin{align}
rk\left(x\cup y\right) &= \sup\{rkz + 1 : z\in x\cup y\}  \\
&=\sup\{\sup\{rkz + 1: z\in x\} , \sup\{rkz + 1 : z\in y\} \} \\
&= \max\{rkx,rky\}
\end{align}
$$
f) $y\in \mathcal P(x) \implies y \subseteq x \subseteq WF \implies y\in WF \implies \mathcal P(x) \subseteq WF \implies \mathcal P(x) \in WF$. Como $y\in \mathcal P(x) \implies rky \leq rkx$  e $x \in \mathcal P(x)$:
$$
rk\left(\mathcal P(x)\right) = \sup\{rkz + 1 : z\in \mathcal P(x)\} = rk(x) + 1
$$
