# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Lógica Proposicional](#Lógica Proposicional)
  - [Proposiciones](#Lógica Proposicional#Proposiciones)
    - [Resumen de proposiciones](#Lógica Proposicional#Proposiciones#Resumen de proposiciones)
  - [Implicación](#Lógica Proposicional#Implicación)

</div>
{{<toc>}}

# Lógica Proposicional

## Proposiciones
Las proposiciones que vamos a usar son e letra minúscula, normalmente se usan 
$p$, $q$, $r$, $s$, $t$, $u$ y $v$.

Las proposiciones son afirmaciones, o aserciones definitivas, donde se declaran
un hecho o suceso, donde la respuesta sobre su veracidad, que puede ser tanto
falso o verdadero. 

Por ejemplo, podemos, si decimos, "Hoy es Falso", sabemos que
$p \equiv F$.

También lo que podemos hacer es componer proposisciones, tales como:

$$
q = \text{Hoy es lunes}
$$
$$
p = \text{Hoy llueve} 
$$

De la misma forma podríamos negarlo, como $\neg q = T$.
Otra cosa que se podría hacer es hacer una **conjunción**, como:

$$
p \land q = \text{Hoy es lunes y llueve}
$$

Otro tipo de operación es la **disyunción**, que se escribe como a
continuación, que puede ser los dos verdaderos, o solo uno de los dos, para que
sea verdadero.

$$
p \lor q = \text{Hoy es lunes y/o llueve}
$$

Una operación un poco distinta es un **ó inclusivo**, que solo da la
posibilidad que ona sea verdadera:

$$
p \oplus q = \text{Hoy es lunes y/o llueve}
$$

También existe la **implicación**, que significa que si un valor es verdadero,
el otro es por lógica también verdadero. Se escribe como:

$$
p \implies q = \text{Si es lunes, llueve}
$$


### Resumen de proposiciones

| Operacion       | Explicación                            |
| --------------- | ---------------                        |
| $\neg q$        | Niega $q$.                             |
| $p \land q$     | Afirma tanto $q$ como $p$              |
| $p \lor q$      | Afirma $q$ y/o $p$                     |
| $p \oplus q$    | Afirma $q$ o $p$                       |
| $p \implies q$  | Si $q$ es verdadero, $p$ también       |


## Implicación

Dentro de la implicación, podemos tener otros casos, tales como:

- **Reciproca:**  $p \implies q : q \imples p$
- **Contrareciproca:** $p \implies q : \neg p \implies \neg q$
- **Inversa:** $p \implies q : \neg q \implies \neg p$

Se puede decir, que por ejemplo, dos expresiones son lógicamente equivalente
cuando para las mismas proposiciones, se dan las mismas respuestas. Esto te
permite probar una proposición a partir de demostrar su contrareciproca.

TODO: Desarrollar doble implicación.




