# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Lógica y razonamiento matemático](#Lógica y razonamiento matemático)
  - [Proposiciones](#Lógica y razonamiento matemático#Proposiciones)
    - [Resumen de operadores](#Lógica y razonamiento matemático#Proposiciones#Resumen de operadores)
  - [Tautología, contradicción y contingencia](#Lógica y razonamiento matemático#Tautología, contradicción y contingencia)
  - [Implicación](#Lógica y razonamiento matemático#Implicación)
    - [Implicación simple](#Lógica y razonamiento matemático#Implicación#Implicación simple)
    - [Implicación Reciproca](#Lógica y razonamiento matemático#Implicación#Implicación Reciproca)
    - [Implicación Contrareciproca](#Lógica y razonamiento matemático#Implicación#Implicación Contrareciproca)
    - [Implicación Inversa](#Lógica y razonamiento matemático#Implicación#Implicación Inversa)
    - [Doble implicación](#Lógica y razonamiento matemático#Implicación#Doble implicación)
  - [Precedencia](#Lógica y razonamiento matemático#Precedencia)
- [Equivalencias lógicas](#Equivalencias lógicas)
- [Predicados y cuantificadores](#Predicados y cuantificadores)
  - [Cuantificador existencial](#Predicados y cuantificadores#Cuantificador existencial)
  - [Cuantificador universal](#Predicados y cuantificadores#Cuantificador universal)
  - [Cuantificador anidado](#Predicados y cuantificadores#Cuantificador anidado)
- [Método de Demostración](#Método de Demostración)
  - [Terminología](#Método de Demostración#Terminología)
  - [Razonamientos válidos](#Método de Demostración#Razonamientos válidos)
  - [Métodos de demostración](#Método de Demostración#Métodos de demostración)
    - [Ejemplo](#Método de Demostración#Métodos de demostración#Ejemplo)
- [Conjuntos](#Conjuntos)

</div>
{{<toc>}}

# Lógica y razonamiento matemático

## Proposiciones
Las proposiciones que vamos a usar son e letra minúscula, normalmente se usan 
$p$, $q$, $r$, $s$, $t$, $u$ y $v$.

Una **preposición**  es toda enunciado que sea verdadero o falso, pero no
ambas a la vez.

En palabras propias, sería: las proposiciones son afirmaciones, o aserciones
definitivas, donde se declaran un hecho o suceso, donde la respuesta sobre su
veracidad, que puede ser tanto falso o verdadero. 

También tenmos la **Tabla de Verdad**, que presenta el resultado de una
proposición compuesta, a partir de todas las combinaciones posibles de los
valores de las proposiciones que lo componen.

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

## Tautología, contradicción y contingencia

Es una composición de proposiciones que siempre es igual, tal como: 
- $p \land \neg p$ siempre va a ser Falso.
- $\neg q \lor q$ siempre va a ser Verdadero.

Luego, similarmente, si tenemos una proposición compuesta que siempre es falsa,
no importando los VV de sus proposiciones componentes, se denomina
**contradicción**. Y últimamente, si tenemos un caso donde se dan los dos, es
una **contingencia**.

---

## Implicación

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

Esto siempre tiene los mismos VV que:

$$
(p \implies q) \land (q \implies p)
$$

## Precedencia

Lo principal para poder marcar la precedencia es a partir de paréntesis, como: 
$(p \lor q) \land (\neg r)$. Pero, luego, la precedencia es:
1. Negación.
2. Conjunción.
3. Disyunción.
4. Implicación.
5. Doble implicación.

# Equivalencias lógicas

Tendremos una **equivalencia lógica** cuando $p \iff q$ es una tautología, es
decir, $p \equiv q$. Es importante entender que $\equiv$ no es un conectivo
lógico.

# Predicados y cuantificadores

- Sea P(x) un enunciado que incluye a la variable $x \in D$, se denomina
  Función Proposional, o predicado, al enunciado $P$ si, para cada valor 
  $x \in D$, se tiene que $P(x)$ es una proposición.
- Se denomina Dominio de Discurso (DD) al conjunto $D$ del enunciado $P$.

TODO: Completar

## Cuantificador existencial

La *cuantificación existencial* de la función proporcional $P$ con dominio de
discurso $D$, es la proposición: $P(x)$ es verdadera para **al menos un** valor
$v$ en el DD. Se nota como: $\exists x, P(x)$, donde $\exists$ es el 
**cuantificador existencial**.

## Cuantificador universal

La cuantificación universal de la función proporcional $P$ con $DD$ es la
proposición: $P(X)$ es verdadera para todos los valores $x$ en el $DD$. Se
denota como $\forall x, P(x)$.


## Cuantificador anidado

Ver ejemplo del apunte. En resumen:

- $\exists x \exists y P(x,y)  \equiv \exists y \exists x P(x,y)$: Conmutan.
- $\forall x \forall y P(x,y)  \equiv \forall y \forall x P(x,y)$: Conmutan.
- $\forall x \exists y P(x,y)  \neq \exists y \forall x P(x,y)$: No conmutan.

# Método de Demostración

## Terminología

- **Axioma:** es una suposición no demostrable y que se supone verdadera.
- **Definición:** es una oración declarativa que describe con precisión el
  significado y alcance de un término.
- **Demostración:** es una serie de proposiciones conexas que definen un
  razonamiento. Se usan para construir nuevas proposiciones a partir de las ya
  dadas, donde las últimas pueden ser axiomas o lemas.
- **Reglas de inferencia:** son proposiciones compuestas tautológicas.
- **Teorema:** es un enunciado escrito como una implicación que se demuestra
  como verdadero usando una demostración.
- **Lema:** teorema auxiliar o de menor alcance, que se usa para demostrar un
  teorema más importante.
- **Corolario:** una consecuencia de un teorema ya demostrado.
- **Falacia:** es una forma de razonamiento incorrecta.
- **Paradoja:** es una inconsistencia lógica. 
- **Conjetura:** es una proposición cuyo valor de verdad es desconocido.


## Razonamientos válidos

Un **razonamiento** (o argumento) es una implicación formada por $n$
proposiciones de la forma:

$$
(p_1 \land p_2 \land ... \land p_n) \implies q
$$

Se dice que un razonamiento es *valido si siempre que TODAS las premisas son*
*$T$, la conclusión también lo es*. Esto nos permite decir que podemos demostrar
que la conclusión $q$ se deduce lógicamente de las premisas $p_1, p_2, ... p_n$.

Una forma para chequear un razonamiento válido es armar una tabla de verdad, y 
mirar *únicamente* las filas en donde toas las premisas son T, y chequear que
*siempre* se tiene una una conclusión $q$ T.

## Métodos de demostración

Existen varias formas de demostración, por ejemplo:

- **Demostración directa:** la implicación $p \implies q$se puede probar
  comprobando si $p$ es T, entonces $q$ también lo es.
- **Demostración indirecta:** como la implicación $p \implies q$ se puede
  probar demostrando que su contra-positiva (o contra-recíproca) es T.
- **Demostración vacua:** cuando $p$, que es la premisa, es siempre F, por lo
  tanto la implicación será siempre será verdadera.
- **Demostración trivial:** cuando $q$ siempre es T, entonces la implicación
  siempre será T, porque cuando $p$ es F, la implicación es T, y cuando es T,
  la implicación también lo es.
- **Demostración por reducción al absurdo.** 
- **Demostración por resolución.**


### Ejemplo

Los únicos enteros consecutivos no negativos $a$, $b$ y $c$ que satisfacen la
siguiente ecuación son 3, 4 y 5:

$$
a^2 + b^2 = c^2 
$$


# Conjuntos

Los conjuntos se emplean para agrupar *cosas* que tienen propiedades parecidas. 
Una definición más formal sería:

> Es una colección de *elementos*, en donde se admite la presencia de elementos
>  repetidos y no necesariamente ordenados. Un *elemento* es cualquier entidad 
> cuya naturaleza interna no interesa y puede ser cualquiera.

Se dice que cada elemento **pertenece** al conjunto, y que un conjunto
**contiene** a sus elementos.

Algunos conjuntos especiales son el conjunto universal *U* o el conjunto vacío
*V*. Luego podemos definir los conjuntos por tres formas:

- **Extensión:** se enumeran todos los elementos del conjunto, colocándolo
  entre un par de llaves. Notación: ${x_1, x_2, \cdots x_n}$. 
- **Comprensión:** se caracteriza por una propiedad de los elementos. Por
  ejemplo: ${x | x \in \N}$.
- **Diagrama de Venn:** es una representación gráfica en donde se representa el
  conjunto universal y dentro de él figuras cuasi-circulares ubicadas dentro
  del universal.

Se puede decir que dos conjuntos tienen **igualdad** si y sólo si tienen los
mismos elementos.
