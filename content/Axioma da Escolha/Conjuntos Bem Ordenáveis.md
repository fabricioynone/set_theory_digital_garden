O objetivo deste capítulo é provar que todo conjunto é bem ordenável. Para isso, vamos supor que exista uma boa ordenação para o conjunto $\mathcal P(A)\setminus \{\emptyset\}$, podemos subtrair um elemento por vez e ordená-los de acordo com a função de escolha.
Um pensamento natural, porém é que não precisaríamos da existência de uma função escolha para fazer tal coisa, podendo ordená-los tomando "qualquer elemento", não temos, porém, ferramentas suficientes para formar essas escolhas arbitrárias. Se o conjunto fosse bem ordenável, por exemplo, poderíamos escolher o menor elemento. Vejamos a seguir

**Prop.**: São equivalentes:
- a) Existe uma função escolha para $\mathcal P(A)\setminus\{\emptyset\}$;
- b) A é bem ordenável.
*Proof*: 
> Estratégia de Prova: Para a volta, fazer uma função escolha a partir do menor. Para a ida, introduzir um símbolo de função recursivamente que usa a função escolha para ordenar o conjunto.

b) $\implies$ a) Como vimos anteriormente, poderíamos formar uma função escolha escolhendo o mínimo de cada conjunto em $\mathcal P(A)$.
a) $\implies$ b) Suponhamos que exista uma função escolha $c$ para $\mathcal P (A)$, tomemos $b \notin A$ e a vamos introduzir um símbolo funcional $F: ON\to A$ dado por:
$$
F(\alpha) = \begin{cases}
c(A \setminus\{F(\beta) : \beta < \alpha\}), \text{ se } \{F(\beta) : \beta < \alpha\}\neq\emptyset \\
b,  \text{caso contário} \\
\end{cases}
$$
Intuitivamente, o que estamos fazendo aqui, é definido um maior elemento num subconjunto de $A$, retiramos-no e escolhemos o próximo menor elemento a partir da função escolha. 
Façamos algumas observações sobre esse símbolo funcional.
- Existe $\alpha \in ON$ tal que $F(\alpha) = b$. Senão, para todo $\alpha \in ON$, $F(\alpha) = c(A \setminus\{F(\beta) : \beta < \alpha\})$ e, assim, teríamos uma $F$ injetora, em particular, $F|_{h(A)}: h(A)\to A$ seria injetora, absurdo.
Como temos um conjunto não vazio de ordinais $\alpha$ tais que $F(\alpha) = b$, sabemos que existe $\delta$, o menor deles. É claro que $F|\delta: \delta\to A$ é injetora, pois $\forall \beta < \delta$, temos que $F(\beta) = c(A \setminus\{F(\xi) : \xi < \beta\})$ e é sobrejetora, pois $F(\delta) = b$. 
Obtemos, portanto, que $F|\delta$ é uma bijeção de $A$ em $\delta$, portanto, A é bem ordenável pela ordem induzida.

Seguem alguns corolários diretos.

**Corolário**: São equivalentes:
- a) Axioma da Escolha;
- b) Todo conjunto é bem ordenável.

**Corolário**: Para todo conjunto $A$, se cardinal, $|A|$, está bem definido.
*Proof*: Como todo conjunto é bem ordenado, segue que temos um ordinal isomorfo e, portanto, em bijeção com ele, logo, o menor deles existe.

**Corolário**: $f: A \to B$ é sobrejetora, então $|B| \leq |A|$.
*Proof*: Segue do lema que vimos em [[Aritmética Cardinal Básica]], pois vimos que, em particular, $B$ é bem ordenável.


