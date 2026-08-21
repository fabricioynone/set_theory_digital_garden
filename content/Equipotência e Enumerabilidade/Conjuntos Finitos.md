Usaremos lemas, resultados e definições de [[Equipotência]], [[Teorema de Cantor]] e [[Teorema de Cantor-Shröder-Bernstein]].

**Def.**: $A$ é finito se existe $n\in \omega$ tal que $A \approx n$. Se isso ocorre, dizemos que a cardinalidade de $A$ é $n$, caso contrário, dizemos que $A$ é infinito.

**Lema**: Para todo $n\in \omega$ e para todo $X \subseteq n$. Se $X \not= n$, então $X \not\approx n$.
*Prova*: Faremos por indução em $n$. Para $n = 0$, o único subconjunto de $0$ é $0$, vale por vacuidade.
Suponha que o resultado vale para todo $m < n$. Seja $X \subseteq n+1$ tal que $X \not= n\cup\{n\}$. Suponha por absurdo que existe uma $f: n+1 \to X$ bijeção. Dividamos em casos:
- Caso 1: $n\not\in X$. Então $f(n) \not= n$. Como $f$ é injetora, $X'= f[n] \subseteq n$, então, $f\upharpoonright : n\to X'$ é bijetora. Assim, teríamos que $X'\approx n$, absurdo pela hipótese de indução.
- Caso 2: $n\in X$. Seja $k\in n+1$ tq $f(k) = n$. Consideremos $g: n \to X\setminus \{n\}$ dada por 
$$
g(m) = \begin{cases}
f(m), \text{ se } m\not= k,\\
f(n), \text{ se } m = k
\end{cases}
$$
Segue da injetividade de $f$ que $g$ é injetora. Provemos que $g$ é sobrejetora sobre $X\setminus\{n\}$. Como $f$ é sobrejetora, existe $m \in n+1$ tal que $f(m) = y$. Se $m\lt n$ e $m\not=k$, então $g(m) = y$. Se $m = k$, então $g(m) = g(k) = f(n)$. Assim, $g$ é bijetora. Como $X\setminus\{n\} \subseteq n$, segue da hipótese de indução que $X\setminus \{n\} = n$. Logo, $X = n +1$, absurdo.

**Colorário (Sobre Finitude)**: a) Para todos $n,m\in\omega$, $n\preccurlyeq m \Longleftrightarrow m\leq n$;
	b) Para todo $m, n \in \omega$, $m\approx n \Longleftrightarrow m = n$; 
	c) Para todo $A$ (conjunto) finito, existe único $n\in \omega$ tal que $A\approx n$;s
	d) $\omega$ é infinito.
*Prova*: