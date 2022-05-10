---
title: "Unidad 5: Niveles de servicio"
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Concepto de capacidad vial](#Concepto de capacidad vial)
  - [Tipo de circulación](#Concepto de capacidad vial#Tipo de circulación)
- [Nivel de servicio](#Nivel de servicio)
- [Condiciones prevalecientes](#Condiciones prevalecientes)
  - [Condiciones base o ideales](#Condiciones prevalecientes#Condiciones base o ideales)
  - [Niveles de análisis](#Condiciones prevalecientes#Niveles de análisis)
  - [Criterios de análisis](#Condiciones prevalecientes#Criterios de análisis)
- [Autopistas](#Autopistas)
  - [Condiciones básicas](#Autopistas#Condiciones básicas)
  - [Determinación de velocidad de flujo libre](#Autopistas#Determinación de velocidad de flujo libre)
  - [Determinación de tasa de flujo](#Autopistas#Determinación de tasa de flujo)
  - [Determinación del nivel de servicio](#Autopistas#Determinación del nivel de servicio)

</div>
{{<toc>}}

# Concepto de capacidad vial

Considerando la demanda de tránsito como conocida, una medida de **eficiencia**
con la que un sistema vial presenta servicio es su capacidad. La capacidad se
define teóricamente como la tasa máxima de flujo que puede soportar una
carretera. En particular, la capacidad de una infraestructura vial es el máximo
número de vehículos que razonablemente pueden pasar por un punto durante un
intervalo de tiempo bajo las condiciones prevalecientes de la infraestructura
vial del tránsito.

Generalmente se toman intervalos de 15 minutos para la tasa de flujo, y esto es
aplicable tanto para el tránsito actual como para el tránsito futuro.

## Tipo de circulación

- **Sistemas viales de circulación continua:** son aquellas donde no existen
  dispositivos de control de tránsito, es decir el mismo no se ve interrumpido.
- **Sistemas viales de circulación discontinua:** estos si cuentan con
  interrupciones de tránsito. No lo vemos en profundidad.

La determinación se presenta según tengan elementos externos de flujo tales
como semáforos, señales de alto, etc.

# Nivel de servicio

Para medir la calidad del flujo vehicular que se usa este concpeto. Es la
medida cualitativa que describe las condiciones de operaciones del flujo
vehicular, y de su percepción por los usuarios.

Se define gracias a: velocidad, tiempo de recorrido, libertad de maniobras,
comodidad, conveniencia y seguridad.

De los factores que afectan al nivel de servicio distinguimos:

| Factores Internos         | Factores externos       |
| ---------------           | ---------------         |
| Variaciones de velocidad  | Caracteristicas físicas |
| Volumen de tránsito       | Ancho de carriles       |
| Composición del tránsito  | Distancia libre lateral |
| Movimientos direccionales | Pendientes              |
      
# Condiciones prevalecientes

Este concepto aparece en la definición de capacidad vial. Podemos distinguir:

1. Condiciones de infraestructura vial.
2. Condicioens del medio ambiente.
3. Condiciones del tránsito.
4. Condiciones de los controles.

## Condiciones base o ideales

Estas son condiciones de referencia óptima y específica, que deberá ser
ajustada para tener en cuenta las condiciones prevalecientes en cada caso de
estudio. Estas asumen: buen estado del tiempo, buenas condiciones del
pavimento, usuarios no existencia de impedimentos en el flujo vehicular.

Dependiendo de cada tipo de sistema de estudio, existirá una serie de
condiciones base específicas para cada uno de ellos, pero en general se puede
plantear una condición prevaleciente en función de la condición base de la
siguiente forma:

$$
 \begin{align}
  \text{Condiciones prevaleciente } = \text{ Condicion base } - \text{ Ajuste Condicion Prevaleciente } 
 \end{align}
$$

Otra alternativa es la multiplicación de la condición base por un factor de ajuste.

## Niveles de análisis

Se consideran tres tipos de análisis según el procedimiento HCM2010:

- Análisis operacional.
- Análisis de diseño: se usa para establecer características físicas que
  permitan a un nuevo sistema vial.
- Análisis de planeamiento: esta dirigido hacia estrategia en el largo plazo
  cuando se empieza a planear un elemento del sistema vial.

## Criterios de análisis

Los factores externos que afectan el nivel de servicio, como son físicos,
pueden ser medidos en cualquier momento a diferencia de los internos, que al
ser variables, deben ser medidos durante el período de mayor flujo, como puede
ser para conseguir el FHMD.


# Autopistas

Las condiciones de operación se puede ver en distintos niveles, con letras
desde A a F. Los más importantes son el **A**, el **E** y el **F**. En el
**E**, el flujo es inestable, pero la capacidad sigue dando a basto a un
tránsito continuo. Por otro lado, en una condición **F** el sistema colapsa,
generalmente generando congestiones.

## Condiciones básicas

- Carriles con ancho mínimo de 3.6m.
- Mínima distancia lateral libre a la derecha de 1.8m.
- Mínima distancia lateral libre a la izquierda de 0.6m.
- Todos los vehículos de la corriente de tránsito son vehículos livianos.
- En áreas urbanas, la autopista deberá tener 5 o más carriles por sentido.
- Espaciamiento entre intercambiadores cada 3km o más.
- Terreno plano con pendientes inferiores al 2%.
- Población de conductores compuesta principalmente de usuarios regulares y
  familiarizados con la autopista.

Estas condiciones representan un alto nivel de operación con flujo libre de
hasta 120km/h. Cualquier diferencia con las condiciones reales implica
reducciones.

## Determinación de velocidad de flujo libre

Es la velocidad media de los vehículos livianos, y puede ser medida en campo o
indirectamente. 

Si la medida es en campo, debe realizarse en un sitio representativo del
segmento estudiado, durante flujos bajos a moderados (hasta 100veh/h) y deben
promediarse las velocidades de al menos 100 vehículos livianos.

Si se dispone de mediciones de campo, se puede estimar indirectamente a partir
de una *velocidad a flujo libre base* que debe ser ajustada para tener en
cuentas las caracteristicas físicas reales del segmento estudiado como:

$$
 \begin{align}
  FFS = BFFS - f_{LW} - f_{LC} - f_{N} - f_{ID}
 \end{align}
$$

Donde cada uno de los ajustes son, respectivamente: ajuste por ancho de carril,
ajuste por distancia libre lateral a la derecha, ajuste por número de carriles
y ajuste por densidad de intercambiadores.

## Determinación de tasa de flujo

Debe reflejar la variación temporal del flujo vehicular dentro de la hora, la
influencia de vehículos pesados y la características de la población de
conductores:

$$
 \begin{align}
  v_p = \frac{V}{FHMD*N*f_{HV}*f_p}
 \end{align}
$$


Donde los factores son:
- $f_{HV}:$ factor de ajuste por presencia de vehículos pesados. Este se debe
  obtener de una formula, con unos valores normales de 15-18% pesados, 5%
  colectivos y 1% recreacionales.
- $f_p:$ factor de tipo de conductores, si están familiarizados o no con la
  autopista. Se puede afectar desde 1 a 0.85.

## Determinación del nivel de servicio

Graficamente podemos ver que sobre la base de una velocidad a flujo libre FFS
se construye una curva velocidad flujo de la misma forma que las típicas.

Analíticamente podemos escribir: $D = v_p / S$.


