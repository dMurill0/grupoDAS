# Decisiones de diseño
A la hora de la toma de decisiones cogeremos aproximadamente unos tres requisitos y trabajaremos sobre ellos. 
Cuando se hayan tomado las decisiones sobre éstos, volveremos a coger otros requisitos y así sucesivamente. 

```markdown
# Decisión de diseño 001: Interfaz única

* Estado: [Decidida]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-23] <!-- when the decision was last updated -->

Technical Story: [description | ticket/issue URL] 

## Contexto del problema

Para hacer más sencillo el manejo del sistema, éste debe proporcionar una única interfaz. 
(Visible tanto en smartphone, como en ordeador o tablet).

## Decision Drivers 

* RF25

## Opciones consideradas

* Patrón Facade (fachada)

## Decision final [outcome]

Opción seleccionada: "FACADE", ya que éste patrón se aplica cuando se necesite proporcionar una interfaz  
simple para un sistema complejo.

### Consecuencias positivas 

* Independencia, portabilidad y reutilización.
* Reducción de dependencias entre los subsistemas y los clientes.
* A la hora de modificar las clases de los subsistemas basta con realizar cambios en la interfaz (fachada) y 
que los clientes puedan quedar aislados.

### Consecuencias negativas 

* Si el acceso por parte de los clientes es masivo, podrían acabar usando solamente una pequeña parte de la fachada.



# Decisión de diseño 002: Sensores geográficos

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-31] <!-- when the decision was last updated -->

## Contexto del problema

Existen sensores geográficos, los cuales detectan si ocurre alguna emergencia en los lugares donde se encuentran   
y envían información al CCR. Los sensores pueden estar colocados de una manera específi􏰄ca o tener una disposición   
totalmente aleatoria, pero en el momento en el que un sensor pase de estar desactivado a activado, el centro de   
control remoto enviará un SMS y una alerta al sistema de emergencias.

## Decision Drivers 

* RF12, RF13

## Opciones consideradas

* Arquitectura dirigida por eventos

## Decision final [outcome]

Opción seleccionada: Arquitectura dirigida por eventos. Los sensores son los generadores,  
es decir, son los que se pueden activar o no; el centro de control remoto está conectado  
con los sensores y recibe la señal si se activan, es el componente de mensajería   
e informa a las partes interesadas, en este caso el sistema de emergencias.

### Consecuencias positivas 

* Detecta un cambio significativo en un estado.
* Simplicidad.
* Una sola modalidad para eventos diversos.
* Mejora la agilidad en los sistemas.

### Consecuencias negativas 

* Hay posibilidad de desborde.
* Potencial imprevisión de escalabilidad
* Pobre comprensibilidad: Puede ser difícil prever qué pasará en respuesta a una acción
* No hay mucho soporte de recuperación en caso de falla parcial


# Decisión de diseño 003: Gestion de llamadas en base a los operadores

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-31] <!-- when the decision was last updated -->

## Contexto del problema

Se requiere que Las llamadas deben entrar tanto al centro de emergencias como al de operaciones mediante una cola y dependiendo de los operadores disponibles.

## Decision Drivers 

* RF13 

## Opciones consideradas

* Patrón Observer (observador)

## Decision final [outcome]

Opción seleccionada: Patrón Observer

### Consecuencias positivas 

* 

### Consecuencias negativas 

* 
# Decisión de diseño 003: Video-vigilancia

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-5] <!-- when the decision was last updated -->

## Contexto del problema

Las cámaras remotas están en contacto con el sistema de emergencias, transmitiéndoles en tiempo real el vídeo.

## Decision Drivers 

* RF3, RF4

## Opciones consideradas

* Patrón Observer (observador)

## Decision final [outcome]

Opción seleccionada: 

### Consecuencias positivas 

* 

### Consecuencias negativas 

* 
