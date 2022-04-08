---
title: Unidad 2 Ingeniería del Software
---

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
  - [Modelos de proceso de software](#Ingeniería de Software#Modelos de proceso de software)
    - [En cascada o waterfall](#Ingeniería de Software#Modelos de proceso de software#En cascada o waterfall)
  - [Modelo incremental o evolutivo](#Ingeniería de Software#Modelo incremental o evolutivo)
  - [Modelo en espiral de Boehm](#Ingeniería de Software#Modelo en espiral de Boehm)
  - [Orientada a la reutilización](#Ingeniería de Software#Orientada a la reutilización)

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

Dentro de la presentación también se ve otra definición:

- Definición de métodos aplicables a cada una de las fases del proceso de
  software.
- Construcción y uso de herramientas para automatizar estos métodos.
- TODO: Completar

La disciplina de la ingeniería de software se interesa por todos los aspectos
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

Algunos tipos de aplicaciones que se pueden ver son:

- **Aplicaciones independientes:** sistemas que corren en una PC local e
  incluyen toda su funcionalidad sin necesidad de una red.
- **Aplicaciones interactivas basadas en transacción:** son aplicaciones que se
  ejecutan remotamente y los usuarios pueden acceder desde su PC, tales como
  aplicaciones web, como comercio web.
- **Sistemas de control embebido:** sistemas de control de software que regulan
  y gestionan dispositivos de hardware. Son los más comunes.
- **Sistemas de procesamientos por lotes:** procesan gran cantidad de entradas
  para producir las salidas correspondientes, tales como sistemas de
  facturación periódica.
- **Sistemas de entretenimiento:** juegos.
- **Sistemas para modelado y simulación:** sirven para modelar procesos o situaciones físicas que incluyen muchos objetos separados. Son computacionalmente intensivos.
- **Sistemas de adquisición de datos:** son sistemas que desde su entorno
  recopilan datos mediante sensores y los envían a otro sistema para su
  proceso.

TODO: Completar con Pág. 12 y 13

## Modelos de proceso de software

No existe un proceso **ideal**. Existen ciertos modelos clásicos, pero
generalmente cada empresa a formado sus propios procesos de desarrollo.

Podemos distinguir los siguientes:

- **Dirigidos por un plan:** son actividades que se planean por anticipado y el avance se mide contra dicho plan. Algunos son:
  - Modelo en casada.
  - Desarrollo incremental o evolutivo.
  - Ingeniería de software orientada a reutilización.
- **Procesos ágiles:** la planeación es incremental, y es más fácil de
  modificar el proceso para cambiar los requerimientos cambiantes del cliente.

Por **ciclo de vida** se entiende la sucesión de etapas por las que pasa el
software desde que un nuevo proyecto es concebido hasta que se deja de usar.
Cada una de estas etapas lleva una serie de tareas y documentación que serán la
salida de cada una de estas fases y servirán de entrada en la fase siguiente.

### En cascada o waterfall

Este paradigma es el más antiguo y se desarrolló a partir del ciclo
convencional de una ingeniería.

Cuenta de las siguientes etapas:

**Etapa 1: Ingeniería y análisis del sistema:** se analiza el software dentro
de un sistema mayor, por lo que siempre va interrelacionado otros elementos
tales como hardware y software. Se le asigna al software las funciones que
cumplirá.

**Etapa 2: Análisis de requisitos de software:** se detallan los requisitos de
los componentes del sistema que se van a implementar mediante software. Esto
debe documentarse y revisarse con el cliente.

**Etapa 3: Diseño:** se da para cuatro características: estructura de datos,
arquitectura de las aplicaciones, estructura interna de los programas e
interfaces. El diseño es el proceso que traduce los requisitos en una
representación del software. Esto debe documentarse y forma parte de la
configuración del software.

**Etapa 4: Codificación:** consiste en traducir o programar el diseño a un
formato que sea legible para la máquina. 

**Etapa 5: Prueba:** una vez que se tiene el programa ejecutable, se empieza la
fase de pruebas. El objetivo es que no hayan errores en alguna de las fases
de traducción anteriores. Para ello deben probarse todas las sentencias, no
sólo los casos normales y todos los módulos que forman parte del sistema.

**Etapa 6: Utilización:** se entrega al cliente y comienza su vida útil. 

**Etapa 7: Mantenimiento:** el software sufrirá cambios a lo largo de su vida
útil. Estos cambios pueden ser debidos a tres causas, tales como errores en el
software no detectados antes, actualización o cambios en componentes del
sistema informático, o que el cliente requiera modificaciones funcionales.

**Etapa 8: Sustitución:** la vida del software no es ilimitada y cualquier
aplicación se acaba sustituyendo. Esto es normalmente mejor hacerlo por etapas,
manteniendo ambas versiones funcionando de forma paralela para comprobar que
el sistema nuevo funcione correctamente.

Algunos **problemas** de este sistema son:
- En la realidad los proyectos no siguen un ciclo secuencial.
- Es difícil que se puedan establecer inicialmente *todos* los requisitos del
  sistema. Esto dificulta de aplicar el método clásico.
- Hasta el final del desarrollo no se da una *versión operativa*.

## Modelo incremental o evolutivo

Se basa en la idea de desarrollar una implementación inicial, exponiéndola a
*feedback*, y refinándola a través del mismo. Las actividades de
especificación, desarrollo y validación se entrelazan en vez de separarse con
una rápida retroalimentación entre éstas.

Se pueden dar dos tipos:

- **Desarrollo exploratorio:** donde el objetivo es trabajar con el cliente
  para explorar sus requerimientos. El sistema evoluciona agregando nuevos
  atributos propuestos por el cliente. Desarrolla primero las partes más
  conocidas y luego evoluciona con las propuestas del ciente.
- **Prototipos desechables:** es comprender los requerimientos del cliente y 
  entonces desarrollar una definición mejorada de los requerimientos del
  sistema. Se centra en los requerimientos que no se comprenden del todo.

Esto implica que la especificación se va haciendo de forma creciente, donde
cada incremento o versión incorpora algunas funciones que necesita el cliente.

## Modelo en espiral de Boehm

Combina las principales ventajas del ciclo de vida en cascada y waterfall.
Proporciona un modelo evolutivo para el desarrollo de sistemas de software
complejos más realista que el ciclo de vida en cascada.

El proceso de software se presenta como una espiral no como una secuencia de
tareas. Cada ciclo en la espiral, donde cada ciclo representa una fase del
proceso de software. Cada etapa cuenta con una **Planificación**, 
**Desarrollo y probar**, **Análisis de riesgo** y **Establecer objetivos**.

## Orientada a la reutilización

Esto ocurre independientemente del proceso de desarrollo empleado. Esto puede
ser por ejemplo la reutilización de una librería como un componente del nuevo
sistema.

Luego de la especificación de los requerimientos tenemos:

**Análisis de componentes:** dada la especificación de requerimientos se
realiza una búsqueda de componentes que puedan suplir ésta. Generalmente no
existe una coincidencia exacta.

**Modificación de requerimientos:** se modifican los requerimientos para dar
lugar a los componentes descubiertos. 

**Diseño de sistema de reutilización:** se diseña el marco conceptual o se
reutiliza al existente. Los creadores toman en cuenta los componentes que se
reutilizan y organizan el marco de referencia para atenderlo. Es posible que
deba diseñarse algo de software nuevo.

**Desarrollo e integración:** se diseña el software que no puede procurarse de
forma externa y se integra con los otros componentes.

Normalmente los componentes que se reutilizan:
- Servicios web que se desarrollan en concordancia para atender servicios
  estándares y que están disponibles para la invocación remota.
- Colecciones de objetos que se desarrollan como un paquete para su
  integración, como componentes tales .NET o J2EE.
- Sistemas de software independientes que se configuran para usar en un entorno
  particular.


