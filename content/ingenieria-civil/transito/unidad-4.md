# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Flujo de tránsito](#Flujo de tránsito)
  - [Conceptos fundamentales con flujos](#Flujo de tránsito#Conceptos fundamentales con flujos)
    - [Tasa de flujo $q$ y volumen $Q$](#Flujo de tránsito#Conceptos fundamentales con flujos#Tasa de flujo $q$ y volumen $Q$)
    - [Intervalos](#Flujo de tránsito#Conceptos fundamentales con flujos#Intervalos)
    - [Densidad](#Flujo de tránsito#Conceptos fundamentales con flujos#Densidad)
    - [Ecuación fundamental](#Flujo de tránsito#Conceptos fundamentales con flujos#Ecuación fundamental)
  - [Resumen de formulas:](#Flujo de tránsito#Resumen de formulas:)
    - [Con flujo](#Flujo de tránsito#Resumen de formulas:#Con flujo)
    - [Con densidad](#Flujo de tránsito#Resumen de formulas:#Con densidad)
    - [Con intervalo](#Flujo de tránsito#Resumen de formulas:#Con intervalo)
    - [Con espaciamiento](#Flujo de tránsito#Resumen de formulas:#Con espaciamiento)
    - [Velocidades](#Flujo de tránsito#Resumen de formulas:#Velocidades)

</div>
{{<toc>}}

# Flujo de tránsito

Esta es una de las características utilizadas por los usuarios para
"determinar" la calidad de una vía.

## Conceptos fundamentales con flujos

### Tasa de flujo $q$ y volumen $Q$

La tasa de flujo es la frecuencia a la cual pasan los vehículos por un punto o
sección transversal de un carril. La tasa de flujo es un número de vehículos
$N$ que pasan durante un intervalo especifico de tiempo $T$ inferior a la hora.
También se puede expresar en veh/h.

$$
 \begin{align}
  q = \frac{N}{T}
 \end{align}
$$

###  Intervalos

Los podemos tomar como **intervalo simple** $h_i$, que es el intervalo de
tiempo entre el paso de dos vehículos consecutivos, generalmente expresado en
segundos.

Por otro lado tenemos los **intervalo promedio** $h$, que es el promedio de
todos los intervalos simples, expresado en s/veh.

$$
 \begin{align}
  \bar{h} = \frac{\Sigma h_i}{N-1}
 \end{align}
$$

También se puede decir como aproximación:

$$
 \begin{align}
  \bar{h} = \frac{1}{q} 
 \end{align}
$$

### Densidad

Es el numero $N$ de vehículos que ocupan una longitud especifica $d$ de una
vía. Generalmente se expresa como veh/km, y se expresa como:

$$
 \begin{align}
  k = \frac{N}{d}
 \end{align}
$$

Se puede decir que la inversa de la densidad será eel espaciamiento:

$$
 \begin{align}
  \bar{s} = \frac{1}{k}
 \end{align}
$$

### Ecuación fundamental

Además, se puede decir que la separación promedio $\bar{s}$ será igual al
producto de la velocidad $\bar{v_e}$ y el espaciamiento promedio $\bar{e}$.

Despejando de esto, podemos llegar a la ecuación fundamental del flujo
vehicular:

$$
 \begin{align}
  q = v * k
 \end{align}
$$


## Resumen de formulas:

### Con flujo

$$
 \begin{align}
  q &= \frac{N}{T}  \\\
  q &= \bar{v_e} * k
 \end{align}
$$

### Con densidad
$$
 \begin{align}
  k = \frac{N}{d}
 \end{align}
$$

### Con intervalo
  
$$
 \begin{align}
  \bar{h} &= \frac{\Sigma f_i * h_i}{N-1} \\\
  \bar{h} &= \frac{1}{q}
 \end{align}
$$


### Con espaciamiento

$$
 \begin{align}
  \bar{s} = \frac{c\Sigma }{} \\\
  \bar{s} = \frac{1}{k}
 \end{align}
$$

### Velocidades

Velocidad temporal:

$$
 \begin{align}
  \bar{v_t} = \bar{v_e} + \frac{S_e^2}{\bar{v_e}}
 \end{align}
$$

$$
 \begin{align}
  S_e^2 = \frac{\Sigma (N_j - \bar{N_e})^2}{m}
 \end{align}
$$

$$
 \begin{align}
  \bar{V_e} = \frac{d}{\bar{t}}
 \end{align}
$$
