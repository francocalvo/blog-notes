# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Inducción](#Inducción)

</div>
{{<toc>}}

# Inducción

Sea la proposición cuantificada de la forma $\forall n P(n)$, donde $P(n)$ es
una función proposicional en el entero $n$ mientras que el Dominio de
Definición es el conjunto de todos los enteros $\mathbb{Z}_0^+$ a partir del
entero $n_0$ dado. Entonces el Principio de Inducción Matemática sostiene que
si e cumple tanto el Paso Base como el Paso de inducción, entonces $P(n)$ es
valida para todos los enteros $n > n_0$.

Se puede simbolizar como:

$$
 \begin{align}
  \left[ P(n_0) \land H(k) \right] \implies \left[ \forall n \in \mathbb{Z}_{n0} \text{ se cumple } P(n+1) \right] \\\
  H(k) \equiv (P(k) => P(l+1)) \text{ para algun entero } k \geq n_0
 \end{align}
$$


