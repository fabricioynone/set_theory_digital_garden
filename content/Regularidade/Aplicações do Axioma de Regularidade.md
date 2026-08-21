### Versão mais forte do Axioma da Substituição
Segue o teorema que nos dá uma versão mais forte do Axioma da Substituição, no sentido de que é pedida uma condição mais fraca para que valha a conclusão da Substituição.
Em algumas partes da prova poderão ser omitidos alguns parâmetros.

**Teorema**: Seja $\phi(x,y,A,t_1,\dots,t_n)$, então:
$$
\forall t_1\dots\forall t_n\forall A(\forall x\in A \exists y(\phi(x,y,A,t_1,\dots,t_n)) \to \exists C\forall x\in A \exists y \in C(\phi(x,y,A,t_1,\dots,t_n))
$$
*Proof*: Consideremos $\phi(x,y,A,t_1,\dots,t_n)$:
$$\psi= \alpha\in ON \land \exists y\in V_\alpha(\phi(x,y,t_1,\dots,t_n)\land\forall \beta < \alpha \neg\exists y\in V_\beta(\phi(x,y,A,t_1,\dots,t_n))$$
Isto é, queremos $\alpha$ o menor ordinal tal que exista um $y\in V_\alpha$ que satisfaça $\phi$ com os parâmetros dados. Sabemos que, pelo Axioma da Substituição, segue que
$$
\forall t_1\dots\forall t_n\forall A(\forall x\in A \exists!\alpha\psi(x,\alpha))\to\exists B \forall x\in A \exists \alpha \in B (\psi(x,\alpha))
$$
Verifiquemos o que queremos. Fixemos $t_1,\dots,t_n$ e $A$ quaisquer. Suponhamos que $\forall x\in A \exists y(\phi(x,t,A,t_1,\dots,t_n))$, pela regularidade, sabemos que cada $y \in V_\alpha$ para algum ordinal $\alpha$, seja, então, $\alpha$ o menor ordinal que satisfaz $\exists y \in V_\alpha(\phi(x,y))$. Sabemos que este $\alpha$ é único, assim está satisfeito que para cada $x\in A \exists! \alpha(\psi(x,\alpha))$. Satisfazendo o que precisamos para concluir que $\exists B \forall x\in A \exists \alpha\in B(\psi(x,\alpha))$. 
Consideremos, portanto, $D = B \cap ON$. $\psi(x,\alpha) \implies \alpha \in ON \implies\forall x\in A \exists \alpha \in D$ tal que $\exists y\in V_\alpha (\phi(x,y))$.
Tomemos, portanto, $\beta = \sup D$, como $\alpha \in B \implies V_\alpha \subseteq V_\beta \implies \forall x\in A \exists y \in V_\beta\,\phi(x,y)$, basta tomar $C = V_\beta$.

### Axioma da Escolha a partir de Regularidade
Vejamos que condição é suficiente para que, assumindo regularidade, valha o Axioma da Escolha.

**Teorema**: Assuma que para todo ordinal $\alpha$, $\mathcal P(\alpha)$ é bem-ordenável. Então vale o Axioma da Escolha.
*Proof*: Notemos que, como provar que o Axioma da Escolha é equivalente a todo conjunto ser bem-ordenado, basta provar que todo conjunto é bem-ordenado. Munido do Axioma da Regularidade, porém, é suficiente provar que, para todo $\alpha$, $V_\alpha$ é bem-ordenado. Façamos isso construindo uma boa ordem para cada $V_\alpha$ recursivamente.
Seja $\alpha \in ON$, definamos $\theta = h(V_\alpha)$ e $\prec$ uma boa ordem para $\mathcal P (\theta)$. Definemos, então, para $\gamma \leq \alpha$, uma boa ordem $\prec_\gamma$ em $V_\gamma$.
- Se $\gamma = 0$, tomemos a ordem $\prec_\gamma = \emptyset$ em $V_0 = \emptyset$.
- Se $\gamma = \delta + 1$ e suponhamos que $\prec_\delta$ já foi definida, consideremos $\eta_\delta = tp(V_\delta, \prec_\delta)$ e $e_\delta:\eta_\delta \to V_\delta$ o único isomorfismo de ordem entre $\eta_\delta$ e $V_\delta$. 
	Como $V_\delta \subseteq V_\alpha$, temos que $\eta_\delta < \theta$. Definamos, para cada $X \in V_\gamma = V_{\delta + 1}= \mathcal P(V_\delta)$
	$$
	c_\delta(X) = e^{-1}_\delta[X]
	$$
	Assim, temos claramente uma bijeção entre $\mathcal P(V_\delta)$ e $\mathcal P(\eta_\delta)$. Como $\eta_\delta < \theta$, temos que $\mathcal P(\eta_\delta) \subseteq \mathcal P(\theta)$, podemos definir, então, para $X, Y \in \mathcal P(V_\delta)$:
	$$
	X \prec_{\gamma} Y \Longleftrightarrow c_\delta(X) \prec c_\delta(Y)
	$$
	Notemos que, por $\prec$ ser boa-ordem em $\mathcal P(\theta)$ que $\prec_\gamma$ é boa ordem em $V_\gamma$.
- Se $\gamma$ é ordinal limite e suponhamos que $\prec_\delta$ foi definida para todo $\delta < \gamma$, consideremos:
$$
x \prec_\gamma y \Longleftrightarrow \begin{cases}
rank(x) < rank(y), \text{ se } rank(x)\neq rank(y) \\
x \prec_{rank(x) + 1} y, \text{ se } rank(x) = rank(y)
\end{cases}
$$
	É claramente total, pois, dados dois conjuntos, seus ranks são comparáveis. Provemos que é boa ordem em $V_\delta$. Seja $S \subseteq V_\gamma$, seja $\alpha = rank(x)$ o menor rank de $S$, tomemos:
	$$
	S \cap \{x\in V_\gamma : rank(x) = \alpha\}
	$$
	O menor elemento de $\prec_{\gamma + 1}$, então, é o menor elemento de $S$.
Assim, para cada $\alpha$, $V_\alpha$ é bem-ordenável, segue, pelo que dissemos no começo da prova, o Axioma da Escolha.