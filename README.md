# blog-robotica-movil-24-25-marcosuse

# Tabla de Contenidos
1. [practica](#practica)
2. [logic](#logic)
3. [problems](#problems)

# practica
el programa esta concebido para resolver el problema de una "rumba" que es un robot autonomo que se usa para limpiar una casa, esta rumba se supone que es (por asi decirlo) tonta ya que no puede acceder a su posicion dentro del mapa por lo que esto complica mucho su funcionamiento eficciente ya que tienes que recurrir a el uso de de la aletoriedad para poder recorrer vien la casa. 

## Hardware
para este programa contamos con principalmente dos tipos de sensores.
### Bumper
Uno de los sensores es el bumper que tras poner un comando nos devolvera 0 en caso de que no se choque con nada y 1 en caso de que se choque.
tambien cuenta con 3 diferentes bumpers a cada lado que tras poner otro comando nos devolvera 0, 1 o 2 dependiendo del bumper con el que se choque.
### Laser
Otro de los sensores que tenemos en funcionamiento es el laser, este cuenta con un angulo de 180 desde el lateral de el robot y funciona emitiendo luz láser pulsada en el entorno. Estos impulsos viajan a la velocidad de la luz, rebotan en los objetos circundantes y vuelven al sensor de esta forma calculando el tiempo en el que tardan puedes saber donde se encuentran las cosas.

# logic
la logica de mi programa siguiendo el siguiente diagrama de estados:

![Texto alternativo](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/Diagrama_vacumm.drawio.png)
