# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Lógica y razonamiento matemático](#Lógica y razonamiento matemático)
- [Proposiciones](#Proposiciones)
    - [Resumen de operadores](#Proposiciones#Resumen de operadores)
  - [Tautología](#Proposiciones#Tautología)
- [Implicación](#Implicación)
    - [Implicación simple](#Implicación#Implicación simple)
    - [Implicación Reciproca](#Implicación#Implicación Reciproca)
    - [Implicación Contrareciproca](#Implicación#Implicación Contrareciproca)
    - [Implicación Inversa](#Implicación#Implicación Inversa)
    - [Doble implicación](#Implicación#Doble implicación)
  - [Precedencia](#Implicación#Precedencia)

</div>
{{<toc>}}

# Lógica y razonamiento matemático

# Proposiciones
Las proposiciones que vamos a usar son e letra minúscula, normalmente se usan 
$p$, $q$, $r$, $s$, $t$, $u$ y $v$.

Las proposiciones son afirmaciones, o aserciones definitivas, donde se declaran
un hecho o suceso, donde la respuesta sobre su veracidad, que puede ser tanto
falso o verdadero. 

Por ejemplo, podemos, si decimos, "Hoy es Falso", sabemos que
$p \equiv F$.

También lo que podemos hacer es componer proposiciones, tales como:

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

Una operación un poco distinta es un **disyunción exclusiva**, que solo da la
posibilidad que una sea verdadera:

$$
p \oplus q = \text{Hoy es lunes y/o llueve}
$$

También existe la **implicación**, que significa que si un valor es verdadero,
el otro es por lógica también verdadero. Se escribe como:

$$
p \implies q = \text{Si es lunes, llueve}
$$


### Resumen de operadores

| Operacion       | Explicación                      | 
| --------------- | ---------------                  |
| $\neg q$        | Niega $q$.                       |
| $p \land q$     | Afirma tanto $q$ como $p$        |
| $p \lor q$      | Afirma $q$ y/o $p$               |
| $p \oplus q$    | Afirma $q$ o $p$                 |
| $p \implies q$  | Si $q$ es verdadero, $p$ también |

* La implicación **no** es un operador lógico.

## Tautología 

Es una composición de proposiciones que siempre es igual, tal como: 
- $p \land \neg p$ siempre va a ser Falso.
- $\neg q \lor q$ siempre va a ser Verdadero.

---

# Implicación

Dentro de la implicación, podemos tener otros casos, tales como:

- **Reciproca:**  $p \implies q : q \implies p$
- **Contrareciproca:** $p \implies q : \neg p \implies \neg q$
- **Inversa:** $p \implies q : \neg q \implies \neg p$

Se puede decir, que por ejemplo, dos expresiones son lógicamente equivalente
cuando para las mismas proposiciones, se dan las mismas respuestas. Esto te
permite probar una proposición a partir de demostrar su contrareciproca.

La **doble implicación** significa lo siguiente:

$$
p \iff q \equiv (q \implies p) \land (p \implies q)
$$


### Implicación simple

La **equivalente lógica** o implicación es falsa solo cuando en $p \implies q$,
$p$ es verdadera y $q$ falsa. Entonces:

| $p$              | $q$             | $p \implies q$  |
| ---------------- | --------------- | --------------- |
| 0                | 0               | 1               |
| 0                | 1               | 1               |
| 1                | 0               | 0               |
| 1                | 1               | 1               |

Otras definiciones, son:

- Si, $p$, entonces $q$.
- Si $p$, $q$.
- $p$ es suficiente para $q$.
- $p$ implica $q$.
- Una condición necesaria para $p$ es $q$.
- $p$ solo si $q$.
- Una condición suficiente para $q$ es $p$.
- $q$ siempre que $p$.
- $q$ es necesaria para $p$.
- $q$ se deduce de $p$.

### Implicación Reciproca

Si a partir de "si $p$, entonces $q$", se define la reciproca como:

$$
p \implies q  \xrightarrow{\text{reciproca}} q \implies p
$$

### Implicación Contrareciproca

Si a partir de "si $p$, entonces $q$", se define la contrareciproca como:

$$
p \implies q  \xrightarrow{\text{contrareciproca}} \neg q \implies \neg p
$$

### Implicación Inversa

Si a partir de "si $p$, entonces $q$", se define la contrareciproca como:

$$
p \implies q  \xrightarrow{\text{inversa}} \neg p \implies \neg q
$$

### Doble implicación

- La doble implicación quiere decir que $p$ es necesario y suficiente para $q$.
- $p$ si y solo $q$.
- si $p$ entonces $q$ y recíprocamente.
- $p$ ssi (iff) $q$.

Tendremos una **equivalencia lógica** cuando $p \iff q$ es una tautología, es
decir, $p \equiv q$.

## Precedencia

Lo principal para poder marcar la precedencia es a partir de paréntesis, como: 
$(p \lor q) \land (\neg r)$. Pero, luego, la precedencia es:
1. Negación.
2. Conjunción.
3. Disyunción.
4. Implicación.
5. Doble implicación.

