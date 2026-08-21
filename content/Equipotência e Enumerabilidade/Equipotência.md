 **Def.**: Sejam $A$ e $B$ conjuntos. Dizemos que $A$ e $B$ possuem o mesmo número de elementos (ou que são equipotentes) se existe uma função bijetora de $A$ em $B$. Escrevemos $A\approx B$.

**Def.**: Dizemos que a cardinalidade de um conjunto $A$ é menor ou igual à cardinalidade de B se existe uma função injetora de $A$ para $B$. Escrevemos $A \preccurlyeq B$.
Dizemos que a cardinalidade de $A$ é menor que a cardinalidade de $B$ se $A \preccurlyeq B$ e $A\not\approx B$.

**Lema**: Para quaisquer $A,B,C$ conjuntos:
	i) $A \preccurlyeq A$
	ii) $A \preccurlyeq B$ e $B\preccurlyeq C$, então $A\preccurlyeq C$
isto é, satisfazem propriedades de pré-ordem, mais tarde discutiremos o porquê de não enunciar desta forma.
*Prova*: 
- i) $Id_A$ é uma injeção de $A$ em $A$.
- ii) Tome a composta.

Note que toda pré-ordem induz uma relação de equivalência. Mas não podemos definir a relação de equivalência, nem uma pré-ordem como uma relação na Teoria dos Conjuntos, mas nada nos impede de introduzi-la na linguagem. Vejamos um teorema que prova isto.

Primeiro, um lema:

**Lema**: Sejam $A,B,A'$ conjuntos tais que $A' \subseteq B \subseteq A$. Se $A\approx A$, então $B\approx A$.
*Prova*: Vamos construir a bijeção. Para isso, $f:A\to A$' a bijeção e definamos recursivamente uma sequência de conjuntos: 
- $A_0 = A$ e $A_{n+1} = f[A_{n}]$; e
- $B_0 = B$ e $B_{n+1} = f[B_{n}]$.
Afirmamos que $A_{n+1} \subseteq B_n \subseteq A_n$, de fato, por indução, temos: 
- Para $n = 0$: $A_1 = f[A] = A' \subseteq B_0 = B\subseteq A = A_0$.
- Suponha, agora, que vale para $n\in\omega$, isto é, que $A_{n+1} \subseteq B_n \subseteq A_{n}$. Temos que 
$$
A_{n+2} = f[A_{n+1}] \subseteq B_{n+1} = f[B_n] \subseteq A_{n+1} = f[A_n]
$$
A $f$ preserva a "contembilidade", pois ela é injetora e o domínio está contido. Concluindo a indução. 
Definamos, agora,  $C_n = A_n\setminus B_n$. Notemos que $f[C_n] = f[A_n\setminus B_n] = f[A_n] \setminus f[B_{n} =$, pois f é injetora, segue, então, que $C_{n+1} = f[C_n] = A_{n+1}\setminus B_{n+1}$. 

Seja $C = \cup_{n\in\omega}C_n$ e $g: A \to A$ definida por $$
g(x) = \begin{cases}
f(x), \text{ se } x\in C \\
x, \text{ c. c.}
\end{cases}
$$Provemos que é bijetora. Para sobrejeção:
- $g[A] \subseteq B$: tome $x \in A$, se $x \in C$, então $g(x) = f(x)\in f[A]\subseteq B$, que está em $C$ por construção, isto é, existe um $C_n \ni x$. Logo, $g(x) = f(x) \in C_{n+1} \subseteq C$. Por outro lado, se $x\not\in C$, então $x\not \in C_0 = A\setminus B$ , logo, $x\in B$ e, portanto, $g(x) = x$ também estará.
- $B \subseteq g[A]$: tome $y \in B$. Se $y \not\in C$, então $g(y) = y \in g[A]$. Se $y\in C$, então existe $n\in\omega$ tal que $y \in C_n$ e $n > 0$ (pois $C_0 = A \setminus B$), então existe $n = m+1$ tal que $g(y) \in g[C_m] \subseteq g[A]$.
Para injeção, considere que haja $x,x'\in A$ tais que $g(x) = g(x')$.
- Se $x, x'\in C$, segue que $x = x'$ pela injetividade de $f$.
- Se $x,x'\not\in C$, segue que $x = x'$ pela definição de $g$.
- se $x\in C$ e $x' \not\in C$, temos que $f(x) = g(x) = g(x') = x'$, mas teríamos que $f(x) \in C$, mas $x' \not\in C$, absurdo.
Logo, $g$ é bijeção de $A$ em $B$.

