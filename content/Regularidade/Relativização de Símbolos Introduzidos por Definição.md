Se temos uma interpretação $A$ da Teoria dos Conjuntos, podemos relativizar fórmulas cujos únicos símbolos não-lógicos sejam $\in$ e $=$.
Há uma forma canônica de expandir a interpretação $A$ para contemplar também símbolos introduzidos por definiçãwo como $\cap,\cup,\subseteq,$ etc.
Para isso, estenderemos $A$ para que tenha, também, novos síbolos $\subseteq^A, \cup^A, \cap^A,$ etc de modo que os axiomas definicionais desse símbolos sejam verdadeiros em $A$.

*Metadefinição*: Sejam $S$ e $T$ duas Teorias de Primeira Ordem e $A$ uma interpretação de $S$ em $T$. Seja $S'$ uma extensão por definição de $S$.
Estendemos $A$ a uma interpretação de $S'$ em $T$, ainda denotada por $A$, estendendo $T^A$ da seguinte forma:
- Para cada predicado de aridade $n \geq 1$ introduzido por definição em $S'$ com axioma definicional dado por 
$$
\forall x_1,\dots\forall x_n(R(x_1,\dots,x_n)\leftrightarrow \phi(x_1,\dots,x_n))
$$
	Define-se $R^A$ como símbolo de predicado de aridade $n$ tal que 
	$$
	\forall x_1,\dots,x_n((R^A(x_1,\dots,x_n)\leftrightarrow(\land^n_{i = 1}x_i\in A) \land \phi^A(x_1,\dots,x_n)))
	$$
	$$ \forall x_1 \dots \forall x_n \left( R^A(x_1, \dots, x_n) \leftrightarrow \left( \bigwedge_{i=1}^n x_i \in A \land \varphi^A(x_1, \dots, x_n) \right) \right) $$

- Para cada $f$ $n$-ário introduzido por definição em $S'$ com axioma definicional dado por
$$ \forall x_1 \dots \forall x_n \forall y (f(x_1, \dots, x_n) = y \leftrightarrow \varphi(x_1, \dots, x_n, y)) $$
	de modo que
$$ S \vdash \forall x_1 \dots \forall x_n \exists! y \varphi(x_1, \dots, x_n, y), $$
	segue que
$$ T^A \vdash \forall x_1 \in A \dots \forall x_n \in A \exists! y \in A (\varphi^A(x_1, \dots, x_n, y)) \text{ e } \therefore \text{ que} $$$$ T^A \vdash \forall x_1 \dots \forall x_n \exists! y \left[ \left(\bigwedge_{i=1}^n x_i \in A\right) \land y \in A \land \varphi^A(x_1, \dots, x_n, y) \right] \lor \left[ \neg\left(\bigwedge_{i=1}^n x_i \in A\right) \land y = x_1 \right] $$
	Assim, define-se $f^A$ pelo axioma definicional
$$ \forall x_1 \dots \forall x_n \forall y \left( f^A(x_1, \dots, x_n) = y \leftrightarrow \left( \left[ \bigwedge_{i=1}^n x_i \in A \land y \in A \land \varphi^A(x_1, \dots, x_n, y) \right] \lor \left[ \neg\left(\bigwedge_{i=1}^n x_i \in A\right) \land y = x_1 \right] \right) \right) $$

	Com essa definição,
$$ T^A \vdash \forall x_1\in A\dots\forall x_n \in A(f^A(x_1,\dots,x_n)\in A)$$
- Para cada símbolo constante $c$ introduzido por definição em $S'$ com axiomada definicional dado por 
$$
\forall y(c = y \leftrightarrow \phi(y)) 
$$
	de modo que
	$$
	S\vdash \exists! y\phi(y)
	$$
	Segue que
	$$
	T^A\vdash \exists!y(y\in A \land \phi^A(y))
	$$
	Assim, define-se $c^A$ pelo axioma definicional
	$$
	\forall y(c^A = y \leftrightarrow \phi^A(y))
	$$
	Com isso,
	$$
	T^A \vdash c^A \in A
	$$