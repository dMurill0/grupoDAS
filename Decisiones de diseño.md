# Decisiones de diseño
A la hora de la toma de decisiones cogeremos aproximadamente unos tres requisitos y trabajaremos sobre ellos. Cuando se hayan tomado las decisiones sobre éstos, volveremos a coger otros requisitos y así sucesivamente. 

<html>
    <head>
        <h1></h1>
    </head>
    <body>
        <table>
        <tr>
          <td><strong>Título</strong></td> 
          <td>Interfaz única</td>
        </tr>
        <tr>
          <td><strong>ID</td>
          <td>ADD-001</td>
        </tr>
        <tr>
          <td><strong>Fecha</td>
          <td>21/10/2019</td>
        </tr>
         <tr>
          <td><strong>Creador de la decisión</td>
          <td>Hamsa Aldrobi, Raquel Alonso</td>
        </tr>
        <tr>
          <td><strong>Estado</td>
          <td>Propuesto</td>
        </tr>
        <tr>
          <td><strong>Requisitos(controlador de decisiones)</td>
          <td>RF25</td>
        </tr>
        <tr> 
          <td><strong>Decisiones alternativas(opciones)</td>
          <td> ADD-002: Patrón Facade (fachada)</td>
        </tr>
        <tr>
          <td><strong>Decisión obtenida (opciones seleccionadas)</td>
          <td>Opción 1: ADD-002. Provee una interfaz unificada simple para acceder a una interfaz o grupo de interfaces de un subsistema.</td>
        </tr>
        <tr>
          <td><strong>Pros Opciones</td>
          <td>-Poder usar una clase ya existente que no se corresponde con la interfaz necesaria.
              -Permite que clases e interfaces incompatibles se puedan usar en conjunto.
              -Facilidad y simplicidad (no hay punteros adicionales.</td>
        </tr>
        <tr>
          <td><strong>Cont. Opciones</td>
          <td>-Inflexibilidad (para las clases) ya que un adaptador sólo puede trabajar con una sola clase, pero no con sus                 hijos a la vez. 
              -Dificultad para definir de nuevo el comportamiento de la clase que ha sido adaptada.</td>
        </tr>
        <tr>
          <td><strong>Enlace hacia otras decisiones</td>
          <td></td>
        </tr>
        <tr>
          <td><strong>Enlace hacia artefactos de arquitectura</td>
          <td></td>
        </tr>             
        </table>
    </body>
</html>
