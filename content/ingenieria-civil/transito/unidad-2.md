---
title: "Unidad 1: Volúmenes de Tránsito"
---

# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Definiciones](#Definiciones)
  - [Generales](#Definiciones#Generales)
  - [Volúmenes de tránsito absolutos](#Definiciones#Volúmenes de tránsito absolutos)
  - [Volúmenes de tránsito medios diarios](#Definiciones#Volúmenes de tránsito medios diarios)
  - [Volúmenes de tránsito horarios](#Definiciones#Volúmenes de tránsito horarios)
- [Características de los volúmenes de tránsito](#Características de los volúmenes de tránsito)
  - [Distribución composición del tránsito](#Características de los volúmenes de tránsito#Distribución composición del tránsito)
  - [Variación de volumen de tránsito en la hora de máxima demanda](#Características de los volúmenes de tránsito#Variación de volumen de tránsito en la hora de máxima demanda)
  - [Volumen de tránsito futuro](#Características de los volúmenes de tránsito#Volumen de tránsito futuro)
    - [Coeficiente de crecimiento ?](#Características de los volúmenes de tránsito#Volumen de tránsito futuro#Coeficiente de crecimiento ?)
    - [Para datos históricos](#Características de los volúmenes de tránsito#Volumen de tránsito futuro#Para datos históricos)

</div>
{{<toc>}}

# Definiciones

## Generales

- **Volumen** $Q$: es el número de vehículos que pasan por un punto durante un
  tiempo específico, expresada como veh/h.
- **Tasa de flujo** $q$: es la frecuencia a la que pasan los vehículos durante
  un tiempo específico menor a una hora, expresada como tasa horaria
  equivalente (veh/h).
- **Demanda** $D$: número de vehículos que desean viajar y pasan por un punto
  durante un tiempo específico. Donde existe congestión, la demanda es mayor a
  la capacidad.
- **Capacidad** $c$: es el número máximo de vehículos que pueden pasar por un
  punto durante un tiempo específico. El volumen nunca puede ser mayor a la
  capacidad.

Podemos definir numéricamente el volumen como:

$$
 \begin{align}
  Q = \frac{N}{t}
 \end{align}
$$

## Volúmenes de tránsito absolutos

Según el lapso loas podemos clasificar en:

- **Tránsito anual (TA):** número total de vehículos que pasan durante un año.
- **Tránsito anual (TM):** número total de vehículos que pasan durante un mes.
- **Tránsito anual (TS):** número total de vehículos que pasan durante una semana.
- **Tránsito anual (TD):** número total de vehículos que pasan durante un día.
- **Tránsito anual (TH):** número total de vehículos que pasan durante una hora.

Además, podemos definir el $Q_i$ como el tránsito en un período menor de una
hora como el total de vehículos que pasan durante un tiempo menor a una hora,
como $Q_{15}$ o $Q_{5}$.

## Volúmenes de tránsito medios diarios

Se define el volumen de tránsito medio diario **TMD** como el número total de
vehículos que pasan durante un periodo dado (días completos) dividido por el
número de días del período. Se escribe como:

$$
 \begin{align}
  TPD = \frac{N}{1 \text{día} < t \leq 1 \text{año}}
 \end{align}
$$

Los más comunes son el TMDA, TMDM y el TMDS.

## Volúmenes de tránsito horarios

Con base a la hora seleccionada, se pueden definir los siguientes volúmenes de
tránsito horario:

- **Volumen horario máximo anual (VHMA):** es el máximo volumen horario que
  ocurre en un punto durante un año determinado. 
- **Volumen horario de máxima demanda (VHMD):** es el máximo número de
  vehículos que pasan por un punto de una calzada durante 60 minutos
  consecutivos. Representa los períodos de máxima demanda que se pueden
  presentar en un día particular.
- **Volumen horario decimo-... (10VH, 20VH, 30VH):** es el volumen horario que
  ocurre en un punto de un carril de un año determinado que es superado solo
  por 9, 19 o 29 volúmenes horarios.
- **Volumen horario de proyecto (VHP):** es el volumen de tránsito horario que
  servirá de base para determinar las características geométricas de la
  vialidad.

# Características de los volúmenes de tránsito

Estos volúmenes son dinámicos, por lo que son precisos para el período de
duración de los aforos. 

## Distribución composición del tránsito

La distribución de tránsito se entiende a como se encuentra distribuido el
mismo en los diferentes carriles o direcciones.

Esto debe ser considerado, ya que por ejemplo, en una zona con tres o más
carriles, el tránsito se asemeja a una corriente hidráulica, debido a
fricciones laterales como paradas de colectivos, taxis o intersecciones. Por
otro lado, para las direcciones, es normal ver variaciones en la dirección
dependiendo la hora entre la zona industrial y el centro de la ciudad.

Por otro lado, la **composición vehicular** es la forma en que se reparte el
volumen total entre los distintos tipos de vehículos, tales como autos,
camiones, motos o bicis.

## Variación de volumen de tránsito en la hora de máxima demanda

La variación de los volúmenes de tránsito dentro de una misma hora de máxima
demanda para una calle puede puede ser repetitiva y consistente durante los
días de la semana, pero puede ser bastante diferente de una calle a otra, por
lo que es importante conocer la variación del volumen dentro de las horas de
máxima demanda y cuantificar la duración de estos flujos máximos.

Un volumen horario de máxima de manda no necesariamente significa que se
conserva la misma frecuencia del flujo durante toda la hora, por lo que existen
varios períodos cortos dentro de una hora con tasas de flujo que van cambiando
y que pueden ser mucho mayores a la hora misma.

Para la hora de máxima demanda, se llama *factor de hora de máxima de manda*
**FHMD** a la relación entre el volumen de horario de máxima demanda VHMD y el
volumen máximo $Q_{max}$ que se presenta durante un periodo dado dentro de
dicha hora. Se expresa como:

$$
 \begin{align}
  FHMD = \frac{VHMD}{N*(Q_{max})}
 \end{align}
$$

Donde $N$ es el número de períodos durante la hora de máxima demanda y $t$ la
duración del período en minutos.

Este factor es un indicador de las características del flujo de tránsito en
períodos máximos. Su mayor valor es la unidad, y significa que existe una
distribución uniforme de flujos máximos en toda la hora. Por otro lado, valores
mucho menores quiere decir que existen concentraciones muy importantes de flujos
máximos.

Lo anterior se puede reescribir como:

$$
 \begin{align}
  q_{max} = \frac{Q_{Hmax}}{FHMD}
 \end{align}
$$

























## Volumen de tránsito futuro

El pronostico del volumen de tránsito futuro **TF** deberá basarse no solamente
en los volumenes normales actuales, sino también en los incrementos del
tránsito que se espera que utilizan la nueva obra.

$$
 \begin{align}
  Tf = Ta + IT
 \end{align}
$$

El tránsito actual $Ta$ es el volumen de tránsito que usará la nueva carretera
o mejorada en el momento de darse completamente el servicio.

En el mejoramiento de una carretera existente, el tránsitoacutal se compone del
*tránsito existente $Te$ antes de la mejora, más el tránsito atraído $T_{at}$,
a ella de otras carreteras.

En el caso de una apretura de una nueva carretera, tenemos:

$$
 \begin{align}
  Ta = Te + T_{at}
 \end{align}
$$

El $Ta$ se puede establecer a partir de aforos vesiculares sobre las vialidades
de la región que influyan en la nueva carretera, estudios de origen y destino,
o utilizando parámetros socio económicos que se identifiquen plenamente con la
economía de la zona.

Por otro lado, el incremento de tránsito $IT$ se desarrolla a partir de tres
factores:

$$
 \begin{align}
  IT = CNT + TG + TD
 \end{align}
$$

Donde los valores son:|
- Crecimiento normal del tránsito (**CNT**): es el que se da naturalmente debido al
  crecimiento del parque automotor.
- Tránsito generado (**TG**): se da por tres factores: tránsito inducido, que son
  viajes que antes no se hacían, tránsito convertido, que es el tránsito que se
  realiza pero por otros medios y tránsito trasladado, que es el tránsito que
  en un principio tenia otro destino, pero que a partir de la nueva vía se
  movió.
- Tránsito desarrollado (**TD**): es el incremento del volumen de tránsito debido a
  las mejoras en el suelo adyacente a la carretera.

### Coeficiente de crecimiento ?

Es un coeficiente que relaciona el tránsito futuro con el tránsito actual. Esto
se desarrolla como:

$$
 \begin{align}
  C_{oef} = \frac{TF}{TA}
 \end{align}
$$


### Para datos históricos

Si tenemos serializados datos históricos de tránsito, se puede realizar una
regresión lineal que nos permitirá hacer aproximaciones tránsito futuro.


