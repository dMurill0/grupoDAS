# Decisiones de diseño
A la hora de la toma de decisiones cogeremos aproximadamente unos tres requisitos y trabajaremos sobre ellos. Cuando se hayan tomado las decisiones sobre éstos, volveremos a coger otros requisitos y así sucesivamente. 

```markdown
# [Interfaz única]

* Estado: [Propuesta]
* Responsables de la decisión: [Hamsa Aldrobi, Raquel Alonso]
* Fecha: [2019-10-23] <!-- when the decision was last updated -->

Technical Story: [description | ticket/issue URL] 

## Contexto del problema

Para hacer más sencillo el manejo del sistema, éste debe proporcionar una única interfaz. (Visible tanto en smartphone, como en ordeador o tablet).

## Decision Drivers 

* [driver 1, e.g., a force, facing concern, …]
* [driver 2, e.g., a force, facing concern, …]

## Opciones consideradas

* Opción 01: Patrón Facade (fachada)

## Decision final [outcome]

Opción seleccionada: "Opción 01", ya que éste patrón se aplica cuando se necesite proporcionar una interfaz simple para un sistema complejo.

### Consecuencias positivas 

* Independencia, portabilidad y reutilización.
* Reducción de dependencias entre los subsistemas y los clientes.
* A la hora de modificar las clases de los subsistemas basta con realizar cambios en la interfaz (fachada) y que los clientes puedan quedar aislados.

### Consecuencias negativas 

* Si el acceso por parte de los clientes es masivo, podrían acabar usando solamente una pequeña parte de la fachada.
