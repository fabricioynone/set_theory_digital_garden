Usaremos notações, definições e lemas enunciados e provados em [[Equipotência]]

**Teorema (de Cantor-Shröder-Bernstein)**: Para quaisquer $A$ e $B$ (conjuntos), se $A\preccurlyeq B$ e $B\preccurlyeq A$, então, $A \approx B$.
*Prova*: Sejam $f: A\to B$ e $g: B \to A$ bijeções, sabemos que $g\circ f : A \to A'= (g\circ f)[A]$ é bijetora. Sabemos, também, que $A'= (g\circ f)[A] = g[f[A]] \subseteq g[B] \subseteq A$.
Logo, temos que $A'\subseteq g[B] \subseteq A$, pelo lema obtemos que $g[B]\approx A$. Note, também, que $g[B] \approx B$, pois $g$ é injetora. Concluímos, então, que $B\approx g[B] \approx A$.  
