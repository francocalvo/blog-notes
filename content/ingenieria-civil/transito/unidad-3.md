# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Antecedentes](#Antecedentes)
- [Definiciones](#Definiciones)
  - [Velocidad](#Definiciones#Velocidad)
    - [Velocidad de punto](#Definiciones#Velocidad#Velocidad de punto)
    - [Velocidad de tramo](#Definiciones#Velocidad#Velocidad de tramo)
    - [Velocidad media temporal](#Definiciones#Velocidad#Velocidad media temporal)
    - [Velocidad media espacial](#Definiciones#Velocidad#Velocidad media espacial)
    - [Velocidad de recorrido](#Definiciones#Velocidad#Velocidad de recorrido)
    - [Velocidad de marcha](#Definiciones#Velocidad#Velocidad de marcha)
    - [Velocidad de proyecto](#Definiciones#Velocidad#Velocidad de proyecto)
- [Aplicaciones de estudios de velocidad](#Aplicaciones de estudios de velocidad)
  - [Estudios de velocidad de punto](#Aplicaciones de estudios de velocidad#Estudios de velocidad de punto)

</div>
{{<toc>}}

# Antecedentes

Año a año, los vehículos han ido aumentando los niveles de velocidad.

# Definiciones

## Velocidad 

La velocidad se define como:

$$
 \begin{align}
  v = \frac{d}{t}
 \end{align}
$$

Es importante considerar posibles interrupciones en el viaje, por ejemplo,
puede que un tramo sea más "corto" en tiempo gracias a que permite una mayor
velocidad, pero al recorrer más distancia es necesario cargas nafta más
seguido.

### Velocidad de punto

La velocidad de punto de un vehículo $i$, es la velocidad $v_i$ a su paso por
un determinado punto.

### Velocidad de tramo

La velocidad de punto de un vehículo $i$, es la velocidad $v_i$ a su paso a lo
largo de un tramo dado.

### Velocidad media temporal

Es la media aritmética de las velocidades de punto de todos los vehículos que
pasan por el mismo

$$
 \begin{align}
  bar{v}_t = \frac{\Sigma n_i * v_i}{n}
 \end{align}
$$


### Velocidad media espacial

Es la media aritmética de las velocidades de tramo de todos los vehículos que
pasan por el mismo:

$$
 \begin{align}
    \bar{v}_e = \frac{\Sigma n_i * v_j}{n}
 \end{align}
$$

Podemos distinguir que, si los vehículos mantienen su propia velocidad
constante en el mismo tramo, nos permite desarrollar lo siguiente:

$$
 \begin{align}
  \bar{v}_e &= \frac{d}{\frac{\Sigma t_i}{n}} \\\
  \bar{v}_e &= \frac{n}{\Sigma (t_i / d)} \\\
  \bar{v}_e &= \frac{n}{\Sigma \left[ \frac{1}{v_i} \right] }
 \end{align}
$$

### Velocidad de recorrido

Es el resultado de dividir la distancia recorrida, desde el inicio hasta el fin 
del viaje, entre el tiempo total que se empleó en recorrerlac.


### Velocidad de marcha

Es el resultado de dividir la distancia recorrida entre el tiempo durante el
cual el vehículo estuvo en movimiento.

$$
 \begin{align}
  v_m = \frac{d}{t_m}
 \end{align}
$$

Donde $t_m$ es el tiempo de marcha. Para obtener la velocidad de marcha en un
viaje normal, se descontará del tiempo total todo el tiempo que el vehículo
estuvo frenado no por voluntad propia.

### Velocidad de proyecto

Es la velocidad a la cual la circulación es segura para condiciones climáticas
favorables y para un conductor de habilidad media.

Generalmente se adopta mediante ábacos, pero generalmente se toman 140km/h en
Europa y 112km/h en EEUU.

# Aplicaciones de estudios de velocidad

## Estudios de velocidad de punto

La mayor parte de los estudios de velocidad se refiere a la velocidad de los
vehículos en determinado punto de la carretera. Se puede hacer de varias
formas, y tiene varias aplicaciones, tipo tendencias de velocidades, lugares
con problemas de velocidad, planeamiento de operaciones de tránsito, análisis
de accidentes, estudios de antes y después de medidas, proyectos geométricos y
estudios de investigación.



