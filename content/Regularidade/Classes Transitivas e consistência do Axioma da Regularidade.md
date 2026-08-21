Usaremos, principalmente na segunda parte, as nomenclaturas listadas em [[__Nomenclatura - Teoria Axiomática dos Conjuntos]].
### Validade de Axiomas para Classes
**Teorema**: Se $A$ é classe transitiva, então vale o Axioma da Extensionalidade em $A$.
*Proof*: Notemos que queremos verificar que
$$
\forall x\in A \forall y\in A((\forall z\in A (z\in x \leftrightarrow z\in y))\to x = y)
$$
Tomemos, então, $x,y \in A$ tais que $\forall z\in A (z\in x \leftrightarrow z \in y)$. Vamos mostrar ambas inclusões $x \subseteq y$ e $y \subseteq  x$. 
Seja $z\in x$, como $A$ é transitivo, $z \in A$ e, portanto, vale que $z \in y$, i.e. $x \subseteq y$. O outro lado da inclusão é análogo.

**Teorema**: Se $A$ é classe transitiva tal que $A \subseteq WF$, então vale o Axioma da Regularidade em $A$.
*Proof*: Queremos verificar que
$$
\forall x \in A (\exists y \in A (y\in x)\to \exists y \in A(y\in x \land \forall z\in A(z\in x \to z\notin y))) 
$$
Seja $x\in A$ tal que $\exists y\in A(y\in x)$, consideremos o conjunto $x'= \{y\in A : y\in x\}$, sabemos que $x'\subseteq A \subseteq WF$ e, como, pela hipótese, $x'\not=\emptyset$, segue que $x'$ possui $\in$-minimal $y'$.
Temos que $y\in x' \implies y'\in x$ e $y\in A$. Como $y$ é $\in$-minimal em $x'$, $\forall z \in A$, se $z\in x$, então $z\in x'$, logo, $z \notin y'$, pela minimalidade de $y'$.

**Teorema**: Se $A$ uma classe tal que para todos $x,y \in A$, $\{x,y\} \in A$. Então vale o Axioma do Par para $A$.
*Proof*: Queremos verificar que
$$
\forall x\in A \forall y\in A(\exists z \in A(x\in z \land y\in z))
$$
Para $x,y\in A$, tome $z = \{x,y\} \in A$.

**Teorema**: Seja $A$ uma classe tal que $\forall X\in A$, a união $\bigcup X \in A$, então vale o Axioma da União para $A$.
*Proof*: Queremos provar que 
$$
\forall x\in A \exists y\in A \forall z\in A((\exists w\in A(w \in x\land z\in w)) \to z\in y)
$$
Fixe $x \in A$. Tome $y = \bigcup x$. Mostremos que satisfaz o que queremos. Seja $z\in A$ tal que $\exists w \in A(w \in A \land z\in w)$, temos, assim, $z \in w \in x$, logo, $z \in \bigcup x = y$.

**Teorema**: Se $A$ é classe transitiva que tenha como elemento algum conjunto indutivo. Então, o Axioma do Infinito vale para $A$.
*Proof*: Queremos
$$
\begin{align}
\exists I \in A(\exists x\in A (x\in I \land \forall y\in A (y\notin x))&\land  \\
\forall x\in A (x\in I \to \exists y\in A(y\in I\land \forall z\in A (z\in y\leftrightarrow z\in x \lor z = x))))
\end{align}
$$
(para primeira parte, tem um conjunto minimal, para a segunda, para todo $x\in I$, $x + 1 \in I$)
Por hipótese, existe conjunto $I$ indutivo em $A$. Assim, $\emptyset \in I$, portanto, $\emptyset \in A$. A primeira parte, $\forall y\in A(y\notin x)$ claramente vale para $y = \emptyset$.
Seja $x \in A$ tal que $x \in I$, tome $y = s(x)$, como $I \subseteq A$ é indutivo, $s(x) \in A$ e claramente vale o quer precisamos.

**Teorema**: Seja $A$ uma classe transitiva tal que toda função $f$ com dom$f = B$, se $B\in A$ e ran$f \subseteq A$, então $\exists C \in A$ tal que ran$f \subseteq C$, então vale o Axioma da Substituição para $A$.
*Proof*: Seja $\phi(x,y,A,t_1,\dots,t_n)$, queremos verificar que
$$
\begin{align}
\forall t_1\dots\forall t_n\in A \forall B\in A(\forall x\in A (x\in B \to \exists!y\in A\phi^A(x,y,B,t_1,\dots,t_n))\\
\to \exists C \in A \forall x\in A(x\in B \to \exists y\in A (y\in C \land \phi^A(x,y,B,t_1,\dots,t_n)))
\end{align}
$$
Fixemos $t_1,\dots,t_n$ em $A$ e $B\in A$. Suponhamos que $\forall x\in A(x\in B \to \exists! y\in A \phi^A(x,y,B,t_1,..,t_n))$, consideremos $f: B \to A$ dada por $\{(x,y): x\in B \land y\in A \phi^A(x,y,B)\}$ que sabemos que existe pelo Axioma da Substituição (e outros). Sabemos que $\exists C$ tal que ran$f \subseteq C$, afirmamos que este conjunto satisfaz a conclusão do nosso teorema. Verifiquemos:
Seja $x \in A$ tal que $x \in B$ basta tomar $y = f(x)$, sabemos que está em $C \subseteq A$ e, por construção $\phi^A(x,y,B,t_1,\dots,t_n)$.

### Consistência do Axioma da Regularidade
**Prop.**: $WF$, com a relação de pertencimento, interpreta todos os Axiomas da $ZF-P$.
*Proof*: $WF$ é classe transitiva fechada para união, pares e tem $\omega$ como elemento (tem typo aq no doc). Assim, vale os axiomas da União, Par, Infinito, Extensionalidade e Regularidade.
$WF$ satisfaz substituição, pois para $B \in WF$ e $f$ com dom$f = B$ tal que ran$f \subseteq WF \implies$ ran$f \in WF$, logo, satisfaz as condições do teorema anterior e, portanto, vale o Axioma da Substituição.
Para a compreensão, fixado $\phi(x,y,B,t_1,\dots,t_n)$, queremos provar que:
$$
\forall t_1\dots\forall t_n \in WF\forall B \in WF \exists y \in WF \forall x\in WF(x\in y \leftrightarrow x\in B \land \phi^{WF}(x,B,t_1,\dots,t_n))
$$
Fixado $t\in WF$ e $B\in WF$, considere $y = \{x\in B : \phi^{WF}(x,B,t_1,\dots,t_n)\}$ temos que $y\subseteq B \subseteq WF \implies y\in WF$ e satisfaz o que queremos.

**Prop.**: $WF$, com relação de pertencimento, interpreta todos os axiomas da $ZF$.
*Proof*: Resta verificar o da potência, i.e.,
$$
\forall x \in WF \exists y\in WF \forall z\in WF(z\subseteq x \to z \in y)
$$
tome $y=\mathcal P(x) \in WF$

**Prop.**: $WF$, com relação de pertencimento, interpreta todos os axiomas da $ZFC - P$.
*Proof*: Resta AC. Queremos que
$$
\begin{align}
\forall A \in WF((\forall x\in WF(x\in A \to \exists y\in WF(x\in y))\land  \\
\forall x\in WF \forall y\in WF(x\in A \land y\in A\land x \neq y \to \neg\exists z\in WF(z\in x \land z\in y)))) \\
\to \exists C\in WF\forall x\in WF(x\in A \to \exists! y\in WF (y\in WF(y\in x \land y\in C)))
\end{align}
$$
Fixemos $A \in WF$ tal que $\forall x\in WF(x\in A \to \exists y\in WF(y\in x))$ e tal que $\forall x,y \in WF(x,y\in A \land x\neq y \to \not\exists z\in WF(z\in x\land z\in y))$. Notemos que satisfaz as hipóteses do Axioma da Escolha, isto é, da primeira parte, $A \in WF$ e $WF$ é transitiva, temos que se $x \in A$, então $x\neq \emptyset$, da segunda parte, se $x,y\in A$ são distintos, são disjuntos. 
Assim, segue do Axioma da Escolha que existe $C$ tal que $|C\cap x| = 1$ para todo $x \in A$. Sabemos, assim, que $C \subseteq \bigcup A$ (na verdade, não sabemos sobre o "excedente" de $C$, se necessário, podemos definir $C'= C\cap \bigcup A$, sabemos que estará contido em $A$ e que manterá a propriedade de ser uma função escolha para $A$) temos que $C \subseteq \bigcup A \subseteq WF \implies C \in WF$.

**Metateorema**: Axioma da Regularidade é consistente com os demais axiomas. Mais precisamente:
- Con($ZF^--P$) $\to$ Con($ZF-P$)
- Con($ZFC^--P$) $\to$ Con($ZFC-P$)
- Con($ZF^-$) $\to$ Con($ZF$)
- Con($ZFC^-$) $\to$ Con($ZFC$)
*Proof*: Toma-se $WF$ com relação de pertencimento. Pois, como provamos anteriormente, todos os axiomas dos respectivos modelos são teoremas quando incluímos a regularidade, isto é, fazemos uma interpretação do modelo sem-regularidade num modelo incluindo a regularidade, com isso segue de

**Teorema**: Sejam $S$ e $T$ teorias de primeira ordem e seja $T^A$ uma interpretação de $S$ em $T$, então $$
\text{Con}(T) \to \text{Con}(S) 
$$
