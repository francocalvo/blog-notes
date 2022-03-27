# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Ingeniería de Software](#Ingeniería de Software)
  - [Complejidad del Software](#Ingeniería de Software#Complejidad del Software)
  - [Tipos de productos de software](#Ingeniería de Software#Tipos de productos de software)
    - [Sistemas genéricos](#Ingeniería de Software#Tipos de productos de software#Sistemas genéricos)
    - [Sistemas personalizados](#Ingeniería de Software#Tipos de productos de software#Sistemas personalizados)
    - [Sistemas adaptados](#Ingeniería de Software#Tipos de productos de software#Sistemas adaptados)
  - [Evolución de la industria del software](#Ingeniería de Software#Evolución de la industria del software)
  - [La ingeniería en software](#Ingeniería de Software#La ingeniería en software)
    - [Características del software](#Ingeniería de Software#La ingeniería en software#Características del software)
    - [Problemas del software](#Ingeniería de Software#La ingeniería en software#Problemas del software)
    - [Definición de ingeniería de software](#Ingeniería de Software#La ingeniería en software#Definición de ingeniería de software)

</div>
{{<toc>}}

# Ingeniería de Software

Como ya dijimos, los sistemas de software son abstractos e intangibles, y no 
están restringidos por las propiedades de los materiales ni regidos por leyes
físicas ni por procesos de fabricación.

Como hay demasiados tipos de software, por lo que no tiene sentido buscar 
notaciones, métodos o técnicas universales, ya que estos distintos tipos
requieren otros enfoques.

## Complejidad del Software

- Complejidad del dominio del problema: consiste en entender el alcance del
  problema, identificar puntos de conflicto en los requisitos del cliente, por
  que se da, etc.
- Dificultad de gestionar el desarrollo: la tarea principal el equipo de
  desarrollo es dar una ilusión de simplicidad de esa complejidad externa que
  tienen los usuarios. A un equipo más grande, se hace más compleja la
  comunicación y coordinación.
- Flexibilidad del software: se puede expresar casi cualquier clase de
  abstracción. Esta flexibilidad resulta ser una propiedad que seduce
  increíblemente y suele empujar al desarrollador a construir por si mismo
  todos los bloques fundamentales.
- Caracterización de problemas: en una aplicación de gran tamaño pueden haber
  miles de variables. El conjunto de todas ellas, sus valores actuales y la
  dirección de ejecución de cada proceso del sistema constituyen el estado
  actual de la aplicación.

El mal manejo de estos aspectos puede llevar a una ***crisis de software***,
implicando retrasos, mayores costos, y resultados deficientes.

## Tipos de productos de software

### Sistemas genéricos

Desarrollos estandarizados que se venden al mercado abierto. La organización
que desarrolla también controla la especificación.

### Sistemas personalizados

Desarrollados por un contratista para un cliente en particular. El cliente
participa en la especificación.

### Sistemas adaptados

Es un mix de los dos anteriores, donde se toma un sistema genérico para poder 
hacer el sistema personalizado. Un ejemplo son los sistemas SAP.

## Evolución de la industria del software

Al principio, el principal foco fue el del hardware, pero con el tiempo esto 
cambió, y el software implica el mayor costo de un sistema, por lo que se ha 
hecho más foco en porqué cuestan lo que cuestan, porqué llevan tanto tiempo,
porqué es difícil depurarlo completamente y porqué es tan difícil de constatar
el progreso del mismo.

## La ingeniería en software

### Características del software

En general un software se diferencia con otros objetos como el hardware en lo 
siguiente:


1. *El software se desarrolla, no se fabrica:* si bien existen similitudes
   entre ambos, como las fases de diseño, etc. La fase de producción  es muy
   distinta entre el hard y el soft. Esto se ve por ejemplo en la producción a
   gran escala.
2. *El software no se estropea:* se puede ver que excepto por los fallos
   iniciales, que pueden ser depurados (igual que pasa con el hard), no existe
   una etapa final donde suba de vuelta la tasa de fallos. Esto es porque el
   software no se "gasta".
3. *La mayoría del software se construye a medida:* el diseño de hardware se
   realiza en gran medida en base de componentes digitales existentes, cuyas
   características se comprueban en un catálogo y que han sido exhaustivamente
   probados por el fabricante. En cambio en el software no existen "catalogos".
   Si bien se a escrito bastante sobre la reutilización de código, el poder
   hacerlo "interproyecto" es muy complejo.

### Problemas del software

Se dice que más que una crisis, un software puede tener una enfermedad crónica, 
ya que puede arrastrar problemas desde sus inicios. Entre ellos podemos citar:

1. *La planificación y la estimación del costo son muy imprecisas:* es frecuente
  que surjan imprevistos que no estaban recogidos en la planificación inicial.
  Lo que sucede en el software es que generalmente no existe una planificación
  detallada, por lo que es muy complejo dar estimaciones de costos. Esto se da
  porque no se recogen datos sobre el desarrollo de proyectos anteriores o que
  la administración no esta especializada en el desarrollo de software.
2. *La productividad es baja:* los proyectos generalmente tienen una duración
   mucho mayor a la esperada, haciendo que los costos se disparen y la
   productividad y los beneficios disminuyan.
3. *La calidad es mala:* como consecuencia de especificaciones ambiguas se
   puede dar que no se realizan pruebas exhaustivas, por lo que el software
   puede contener numerosos errores cuando se entrega al cliente.
4. *El cliente queda insatisfecho:* debido al poco tiempo e interés que se
   dedica al análisis de requisitos y a la especificación del proyecto, a la
   falta de comunicación, etc.

### Definición de ingeniería de software

La diciplinar de la ingeniería de software se interesa por todos los aspectos
de la producción de software, desde las primeras etapas de la especificación
del sistema hasta el mantenimiento del mismo. Busca seleccionar los métodos más
adecuados para cada tarea, y encuentra 4 puntos comunes:

1. **Especificación:** la especificación del software es donde los clientes e
   ingenieros definen funcionalidades del software que se producirá y las
   restricciones de su operación.
2. **Diseño e implementación:** donde se diseña y programa siguiendo las
   especificaciones.
3. **Validación:** donde se verifica el software para asegurar que sea lo que
   el cliente requiere.
4. **Evolución:** donde se modifica para reflejar los requerimientos cambiantes
   del cliente.

Diferentes tipos de sistemas necesitan distintos tipos de procesos de
desarrollo.
