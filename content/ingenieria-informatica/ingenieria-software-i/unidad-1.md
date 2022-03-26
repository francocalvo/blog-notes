# Table of contents
<div class='hidden'>
# Contents

- [Table of contents](#Table of contents)
- [Introducción](#Introducción)
- [Metodología](#Metodología)
- [Sistema](#Sistema)
  - [Sistema: modelo de control](#Sistema#Sistema: modelo de control)
  - [Sistema de Pilotaje](#Sistema#Sistema de Pilotaje)
  - [Sistema de Información](#Sistema#Sistema de Información)
    - [Aspectos del SI](#Sistema#Sistema de Información#Aspectos del SI)
    - [Acciones programadas y decisiones](#Sistema#Sistema de Información#Acciones programadas y decisiones)
  - [Sistema Automatizado de Información](#Sistema#Sistema Automatizado de Información)
    - [Sub-sistemas funcionales del SAI](#Sistema#Sistema Automatizado de Información#Sub-sistemas funcionales del SAI)

</div>
{{<toc>}}

# Introducción

Los sistemas de software son intangibles, a diferencia del hardware.

# Metodología

Es normalmente necesario tener una metodología, ya que:

- Es beneficioso que tanto usuarios como el equipo de trabajo tengan una 
  buena idea de cuáles son los propósitos de cada etapa y sus respectivas
  fases.
- Únicamente a través metodología ordenada y clara es posible obtener
  resultados satisfactorios de un trabajo en equipo, ya que permite coordinar y
  hacer comprender a cada integrante la participación e integración de su tarea
  con las del resto.
- Permiten fijar con claridad puntos de control, que permiten evaluar la marcha
  de un proyecto.
- Permite hacer de forma gradual:
  - Conocimiento detallado del problema.
  - Diseño de una solución al máximo detalle.
  - Desarrollo de la solución planeada.
- Incrementa la posibilidad de encontrar errores significativos.

# Sistema

Un sistema es un conjunto de elementos materiales o inmateriales en
interacción, que transforman, mediante procesos, elementos de entrada y salida.

Se dice que los sistemas interactúan con sus medios ambientes, es decir, con
elementos que se sitúan fuera de los limites del sistema, donde existen
**fronteras** que los separan. Según si un sistema tiene esta interacción o no 
podemos decir que tenemos un *sistema abierto* o un *sistema cerrado*.
  
## Sistema: modelo de control

Es necesario comparar los rendimientos reales de un sistema con ciertos
**estándares**, y se debe logear lo que se encuentre muy por encima o por
debajo, permitiendo estudiar el caso puntual.

Para esto, los sistemas tienen un modelo de control básico que consiste en:

- Un **estándar**  para rendimiento aceptable.
- Un método de medición del rendimiento **real** .
- Una forma de **comparar**  el rendimiento real contra el estándar.
- Un método de **retro alimentación** .

Un sistema que puede auto-ajustarte a niveles aceptables permite que sigan
funcionando sus procesos, mientras que uno que no puede hacer, se detiene.

El concepto de **interacción** dentro de un medio ambiente de los sistemas
abiertos es esencial para el control, ya que un sistema puede tomar su entrada
y evaluar la misma, determinando que tan bien esta operando.

Por el otro lado, sistemas cerrados que no interactúan con el medio ambiente,
sostienen su operación solamente durante el tiempo que tienen la información
adecuada y no necesiten nada del medio ambiente.

## Sistema de Pilotaje

Un sistema se puede control por otro que se denomina **sistema de pilotaje**.
Este tipo de sistemas decide el comportamiento del sistema controlado, en
función de objetivos fijados. Recibe información desde el sistema operativo, 
sobre su estado, y puede reaccionar mediante decisiones sobre los procesos del
sistema operativo, como regulando el flujo de entrada al mismo.

Todo sistema complejo generalmente agrega como interfaz entre el sistema de 
pilotaje y el sistema operativo un sistema de información.

## Sistema de Información

El sistema de información compone diversos elementos encargados de almacenar y
tratar las informaciones relativas al sistema operativo para ponerlas a
disposición del sistema de pilotaje. Este sistema también puede recibir recibir
decisiones del sistema de pilotaje.

También puede emitir información de interacción hacía el sistema operativo,
ejerciendo acciones sobre el mismo. Por ejemplo, el sistema operativo solo
podrá remitir artículos al cliente si el sistema de información obtiene el dato
de que existe stock del mismo.

Existe una estrecha relación entre el Sistema de Información, el Sistema
Operativo y el Sistema de Pilotaje. Este se denomina **entorno interno**.

Además, el sistema de información presenta interacciones con elementos fuera
del sistema general, quienes se valen del SI para vincularse a nuestro sistema
sin ser parte de él, tales como clientes, proveedores, etc. Esto constituye el
**entorno externo**. Estos dos entornos constituyen el Universo Exterior del
sistema de información.

### Aspectos del SI

Este sistema además funciona como una *memoria* de la organización, por lo
implica un **aspecto estático**:
- Registrando hechos acontecidos en el universo exterior en un conjunto
  memorizado que se podría calificar como base de información.
- Registrando estructuras de datos, reglas y limitaciones del universo
  exterior, de manera formalizada, en un conjunto que se podría clasificar como
  modelo de dominio.

Esto también implica un **aspecto dinámico:** 
- Posibilidad de actualizar los datos memorizados en la base de información.
- Posibilidad de cambiar las estructuras, reglas y limitaciones del modelo de
  dominio.

Esta parte activa se constituye como el **procesador de información**, donde
cada evento del universo exterior constituye un mensaje para el procesador de
información. Luego, el procesador de información, con ayuda de las reglas que
se encuentran en el modelo, interpreta este mensaje y puede realizar
modificaciones a su base de información o a su propio modelo.

### Acciones programadas y decisiones

Todo sistema puede tener dos tipos de acciones, las programadas y las
decisiones. Las **programadas** son aquellas que determinan una manera única
las salidas a partir de las entradas. Esto consistiría en un sistema
determinado.

Un sistema también puede encontrarse con información incompleta, por lo que una
misma entrada podría resultar en varias salidas. En este caso, la elección de
que se devolverá será mediante una **decisión**.


## Sistema Automatizado de Información

Un SAI es un sub-sistema de un sistema de información, en el que todas las
transformaciones significativas de información se efectúan mediante máquinas de
tratamiento automático de la información.

Esto permite la conservación y tratamiento automático de los datos.

### Sub-sistemas funcionales del SAI

En un SAI, el sistema de información se compone por:
- Conjunto de hardware/software y personal.
- Unidades periféricas de comunicación, soportes de toma de datos, etc.
- Modelo y base de información por medio de unidades periféricas de
  almacenamiento.

Donde los últimos dos son parte del Universo Exterior del procesador de
información. Esto nos permite descomponer el SAI en cuatros sub-sistemas
funcionales:

- Dos sub-sistemas internos:
  - Tratamiento automático.
  - Memorización.
- Dos sub-sistemas de interfaz con el Universo Exterior:
  - Recogida de datos.
  - Salidas.

