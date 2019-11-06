# Decisiones de diseño
A la hora de la toma de decisiones cogeremos aproximadamente unos tres requisitos y trabajaremos sobre ellos. 
Cuando se hayan tomado las decisiones sobre éstos, volveremos a coger otros requisitos y así sucesivamente. 

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

```markdown
# Decisión de diseño 001: Interfaz única

* Estado: [Decidida]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-23] <!-- when the decision was last updated -->

Technical Story: [description | ticket/issue URL] 

## Contexto del problema

Necesitamos una interfaz unica para que puedan acceder de la misma forma diferentes dispositivos, que metodo
es el mas adecuado?

Solucion:
Para hacer más sencillo el manejo del sistema, éste debe proporcionar una única interfaz, para diferentes. 
*(Visible tanto en smartphone, como en ordeador o tablet)*

## Decision Drivers 

* RF25

## Opciones consideradas

* Patrón Facade (fachada), ya que se ajusta y se precisa a la interfaz unica para todos los usuarios.

## Decision final [outcome]

Opción seleccionada: "FACADE", ya que éste patrón se aplica cuando se necesite proporcionar una interfaz  
simple para un sistema complejo.

### Consecuencias positivas 

* Independencia, portabilidad y reutilización.
* Reducción de dependencias entre los subsistemas y los clientes.
* A la hora de modificar las clases de los subsistemas basta con realizar cambios en la interfaz (fachada) y 
que los clientes puedan quedar aislados.

### Consecuencias negativas 

* Si el acceso por parte de los clientes es masivo, podrían acabar usando solamente una pequeña parte de   
la fachada.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

# Decisión de diseño 002: Sensores geográficos

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-31] <!-- when the decision was last updated -->

## Contexto del problema

Queremos detectar por medio de sensores, los eventos inesperados que hace que se notifique al sistema 
de emergencias para que se procesen adecuadamente, ¿Qué sistema necesitamos?

Solucion:
Para acceder al estado sensores en los distintos puntos geográficos, agregaremos en el centro de control
remoto un sistema para recoger informacion de estos en tiempo real, para luego poder enviar la   
notificacion al centro de emergencias.

## Decision Drivers 

* RF12, RF13

## Opciones consideradas

* Arquitectura dirigida por eventos

## Decision final [outcome]

Opción seleccionada: Arquitectura dirigida por eventos. Los sensores son los generadores, es decir, 
son los que se pueden activar o no; el centro de control remoto está conectado con los sensores y recibe 
la señal si se activan, es el componente de mensajería e informa a las partes interesadas, en este 
caso el sistema de emergencias.

### Consecuencias positivas 

* Detecta un cambio significativo en un estado.
* Simplicidad.
* Una sola modalidad para eventos diversos.

### Consecuencias negativas 

* Hay posibilidad de desborde.
* Potencial imprevisión de escalabilidad
* Pobre comprensibilidad: Puede ser difícil prever qué pasará en respuesta a una acción
* No hay mucho soporte de recuperación en caso de falla parcial

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

# Decisión de diseño 003: Llamadas distribuidas

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-31] <!-- when the decision was last updated -->

## Contexto del problema

Las llamadas en cola se tienen que asignar a los operadores dependiendo de la disponibilidad de   
estas, ¿Cómo se podrian 
asignar uniformemente?

Solucion:
Un módulo que permita acceder y supervisar el estado de la cola de las llamadas, y que al mismo  
tiempo, asignarlos y priorizarlos a los diferentes operadores inactivos o en pausa.

## Decision Drivers 

* RF11

## Opciones consideradas

* Supervisor Module

## Decision final [outcome]

Opción seleccionada: Supervisor Module

### Consecuencias positivas 

* Acceso en tiempo real a la cola de llamadas
* Priorizacion de tareas
* Se podria ocupar de grabar la conversacion

### Consecuencias negativas 

* El tiempo de espera puede ser exponencial si la cola no va desapareciendo

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# Decisión de diseño 004: Video-vigilancia

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-5] <!-- when the decision was last updated -->

## Contexto del problema

Queremos que existan unas cámaras transmitan en tiempo real vídeo y además, que estos vídeos se guarden  
durante un cierto tiempo para luego borrarse y así no saturar la memoria dinámica. ¿Cómo lo hacemos?

Solución:
Las cámaras remotas están en contacto con el sistema de emergencias, transmitiéndoles en tiempo   
real el vídeo. El sistema tendrá una base de datos que guarde el vídeo durante x tiempo.

## Decision Drivers 

* RF3, RF4

## Opciones consideradas

* SOA Event-Driver

## Decision final [outcome]

Opción seleccionada: 

### Consecuencias positivas 

* 

### Consecuencias negativas 

*

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# Decisión de diseño 004: Algoritmo de optimización

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-5] <!-- when the decision was last updated -->

## Contexto del problema

Necesitamos un algoritmo que calcule las rutas más óptimas para que las unidades lleguen al punto de emergencia   
lo más rápido posible.

Solución:
Existe una interfaz que tendrá todos los algoritmos necesarios para el funcionamiento del programa. En el   
momento en el que una emergencia ocurra y se vaya a notificar a las unidades activas, se debe acceder a   
esta interfaz y seleccionar el método que calcule la ruta más óptima a la emergencia.

## Decision Drivers 

* RF3, RF4

## Opciones consideradas

* Patrón Strategy

## Decision final [outcome]

Opción seleccionada: 

### Consecuencias positivas 

* Permite que el algoritmo pueda variar sin importar los clientes que lo utilicen.
*

### Consecuencias negativas 

*
