Usando notações e resultados que obtivemos em [[Equipotência]] e p[[Teorema de Cantor-Shröder-Bernstein]], podemos mostrar que, pelo Axioma da Potência (Axioma das partes), a "pré-ordem" $\preccurlyeq$ não tem elemento máximal.

**Teorema (de Cantor)**: Para todo $A$ (conjunto), $A \prec P(A)$
*Prova*: Sabemos que $A \preccurlyeq P(A)$ usando a injeção $f: A \to P(A)$ dada por $f(x) = \{x\}$. Basta provar que $A\not\approx P(A)$. 
Seja $g: A \to P(A)$ qualquer. Consideremos $B = \{x\in A : x\not\in f(x)\}$, suponha por absurdo que $B = f(y)$ para algum $y\in A$ (podemos pegar apenas um elemento de $A$, justamente porque $B \subseteq A$, então é um elemento do conjunto das partes), então:
$$
y\in B \Longleftrightarrow y\not\in f(y) \Longleftrightarrow y\not\in B 
$$
Assim, concluímos que $B\not\in f[A]$
