# blog-robotica-movil-24-25-marcosuse

# Tabla de Contenidos
1. [practica](#practica)
2. [logic](#logic)
3. [problems](#problems)

# practica
el programa esta concebido para resolver el problema de una "rumba" que es un robot autonomo que se usa para limpiar una casa, esta rumba se supone que es (por asi decirlo) tonta ya que no puede acceder a su posicion dentro del mapa por lo que esto complica mucho su funcionamiento eficciente ya que tienes que recurrir a el uso de de la aletoriedad para poder recorrer vien la casa. 

## Hardware
para este programa contamos con principalmente dos tipos de sensores.
uno de ellos es el bumper que tras poner el siguiente comando nos devolvera 0 en caso de que no se choque con nada y 1 en caso de que se choque.
```python
HAL.getBumperData().state
```
### Bumper
Uno de los sensores es el bumper que tras poner el siguiente comando nos devolvera 0 en caso de que no se choque con nada y 1 en caso de que se choque.
```python
HAL.getBumperData().state
```
tambien cuenta con 3 diferentes bumpers a cada lado que tras poner el comando a continuacion nos devolvera 0, 1 o 2 dependiendo del bumper con el que se choque.
```python
HAL.getBumperData().bumper
```
### Laser
