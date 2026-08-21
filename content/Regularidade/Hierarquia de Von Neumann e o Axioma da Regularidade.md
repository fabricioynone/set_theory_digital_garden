**Prop.**: Assumindo o Axioma da Potência, para cada $\alpha \in ON$ existe único $V_\alpha \subseteq WF$ tal que:
$$
\forall x \in WF(x\in V_\alpha \leftrightarrow rkx < \alpha)
$$
Para todo ordinal $\alpha$ vale que:
- i) $V_0 = \emptyset$;
- ii) $V_{\alpha + 1} = \mathcal P(V_\alpha)$
- iii) Se $\lambda$ é ordinal limite, então $V_\lambda = \bigcup_{\alpha < \lambda} V_\alpha$
*Proof*: Segue do Axioma da Extensão que o conjunto é único. Provemos que existe usando indução transfinita em $\alpha$. Suponha que vale para todo $\lambda < \alpha$ que $V_\lambda \subseteq WF$ e que
$$
\exists x\in WF(x\in V_\alpha \leftrightarrow rkx <\lambda)
$$
Dividamos em casos:
- i) Se $\alpha = 0$, então $V_\alpha = V_0 = \emptyset$. Como para todo $x$, $rkx \geq 0$, temos $V_o$ como desejado.
- ii) Se $\alpha = \beta + 1$, então tomemos $V_\alpha = \mathcal P(V_\beta)$, como $V_\beta \subseteq WF \implies V_\beta \in WF$, temos que $V_{\alpha} = \mathcal P(V_\beta) \in WF$. Mostremos que $V_\alpha$ satisfaz o que queremos:
$$
x\in V_\alpha \implies x \subseteq V_\beta \implies \forall y\in x(rky \leq \beta) \implies rkx \leq \beta < \beta + 1 = \alpha
$$
$$
x\in WF \land rkx < \alpha \implies rk(x) \leq \beta \implies \forall y\in x(rky < \beta) \implies y \in V_\beta \implies x \subseteq V_\beta \implies x\in V_\alpha
$$
- iii) Se $\alpha$ é ordinal limite, sabemos que $\{V_\lambda : \lambda < \alpha\}$ é conjunto e mostremos que $V_\alpha = \bigcup \{V_\lambda : \lambda < \alpha\}$ satisfaz o que queremos:
$$
rkx < \alpha \Longleftrightarrow \exists\lambda < \alpha (rkx < \lambda) \Longleftrightarrow \exists \lambda < \alpha (x \in V_\lambda) \Longleftrightarrow x \in \bigcup_{\lambda< \alpha} V_\lambda
$$
Dessa forma, em linguagem de classes, 
$$
WF = \bigcup_{\alpha \in ON} V_\alpha
$$
Além disso, para todo $x \in WF$,
$$
rk(x) = \min\{\alpha \in ON : x\in V_{\alpha + 1}\}  \Longleftrightarrow rkx = \min\{x \in ON : x \subseteq V_\alpha\}
$$
 Será que conseguimos construir conjuntos que estão fora da $WF$ ou $\mathbf{V} = WF$? Analisemos o que os axiomas que temos nos dizem sobre a existência de conjuntos fora da $WF$.

**Compreensão**: Diz que certos subconjuntos existem, mas $WF$ é fechada para subconjuntos.
**Par**: Se $x,y$ são bem-fundados, vimos que $\{x,y\} \in WF$
**União**: $\bigcup x$ é bem fundado.
**Substituição**: Seja $A$ e uma expressão que associa $A$ a um único $y$, existe um conjunto desses $y$. Se $y \in WF$, então o conjunto dos $y$ também estará.
**Escolha**: Nos fala coisas sobre certas relações existirem, como o prod cartesiano é bem fundado e as relações são subconjuntos de prod cartesiano, são bem fundados.
**Extensão**: Não parece ter nada relacionado ao nosso problema.

**Teorema**: Todo grupo $G$ é isomorfo a um grupo $G'$ em $WF$. Todo espaço topológico $X$ é isomorfo a um espaço topológico $X' \in WF$.
*Proof*: Seja $G = (S, \cdot)$, sabemos que o Axioma da Escolha implica que existe um $\alpha \in ON$ tal que existe uma bijeção $f: S \to \alpha$. Definamos $G'= (S'= \alpha, \cdot')$ com $\cdot'$ definido por $x \cdot'y = f(f^{-1}(x)\cdot f^{-1}(y))$ é fácil ver que é grupo.

Vimos, então, que tudo sugere que $V = WF$, para oficializar isso, temos:

**Axioma (da Regularidade)**: 
$$
\forall x(\exists y(y\in x) \rightarrow\exists y(y\in x\land \neg\exists z(z\in y\land z\in x)))
$$

**Prop.**: São equivalentes:
- i) Axioma da Regularidade;
- ii) $\in$ é bem fundada
- iii) $WF = V$
*Proof*: i) $\Longleftrightarrow$ ii) é literal. Provemos:
ii) $\implies$ iii) Suponha que $\in$ é bem fundada, seja $x\in V$, $\in$ é bem fundado em $trcl(x)$, logo, x \in WF.
iii) $\implies$ ii) $WF = V$. Seja $x\neq \emptyset$, $x \in WF$ (tem um typo aq) $\implies x\subseteq WF$, logo, $x$ possui um $\in$-minimal y.
