# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Enteros y División](#Enteros y División)
    - [Teorema de divisores](#Enteros y División#Teorema de divisores)
  - [Cociente-residuo](#Enteros y División#Cociente-residuo)
  - [Aritmética modular](#Enteros y División#Aritmética modular)

</div>
{{<toc>}}

# Enteros y División

Es necesario saber la definición y notación de cociente, divisor y el
dividendo.

Se puede decir que $D|A$, es decir que A es divisible por D. Esto lleva los
siguientes teoremas:

1. Si $a|b$ y $a|c$, entonces $a|(b+c)$.
2. Si $a|b$, entonces $a|(b*c)$.
3. Si $a|b$ y $b|c$, entonces $a|c$.

Otra definición importante es la de los **números primos**, que es un número
entero positivo $p$ y mayor a 1 que sus únicos divisores son el 1 y $p$.

Por otro lado, un **número compuesto** es un entero $p$ que *no* es primo. 

### Teorema de divisores

Un entero positivo $n$ mayor a 1 es compuesto si $n$ tiene un divisor $d$ tal
que $2 \leq d \leq \sqrt{n}$. Ver demostración.

## Cociente-residuo

Sea un entero $a$ y un entero positivo $d$, entonces podemos tener:

$$
 \begin{align}
  a = q*d + r
 \end{align}
$$

Donde el valor de $r$ es $0 \leq r < d$.

## Aritmética modular

**Consecuencia:** sean los enteros A y B, y M entero positivo. Se dice que A es
congruente con B en módulo M, si M divide a la diferencia de A y B y se denota 
como $A \equiv B$ (mod M).

