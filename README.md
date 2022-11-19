# VyVS-Tarea09-Tapir

## Especificación para la clase Juego:

### Se definen los siguientes símbolos:
```     
mapMethodsToSymbols.put("logica.Juego.<init>", "c");
mapMethodsToSymbols.put("logica.Juego.generarDisparo", "d");
mapMethodsToSymbols.put("logica.Juego.generarPremio", "p");
mapMethodsToSymbols.put("logica.Juego.setNivel", "n");
mapMethodsToSymbols.put("logica.Juego.perderJuego", "l");
mapMethodsToSymbols.put("logica.Juego.moverJugador", "m");
mapMethodsToSymbols.put("logica.Juego.reiniciarJuego", "r");
 ```
 
### Regex válida:
`c(((d|p|n)*l)*|m)*r`

- `c`: Primero se debe instanciar la clase `Juego`
- `(((d|p|n)*l)*|m)*`: Se realizan las interacciones del juego:
  - `((d|p|n)*l)*`: se pueden realizar 0 o más refrescos de los elementos del juego que pueden incluir
    - `(d|p|n)*`: 0 o más interacciones de **disparos**, **premios**, **cambio de nivel**
    - `l`: siempre debe verificarse si las interacciones provocaron el fin del juego (perder el juego)
  - `m`: ordenar un moviemiento del jugador (por keystroke event, en cualquier momento que no se esté refrescando el juego)
- `r`: se puede reiniciar el juego
 

## Pasos para compilar en IntelliJ
1. Clonar el repositorio
2. Instalar el plugin de AspectJ (requiere IntelliJ IDEA Ultimate que es gratuito para estudiantes y docentes)
3. Actualizar las dependencias con Maven
4. Compilar con `aspectj:compile`, disponible a través de las dependencias añadidas por Maven (puede ser necesario compilar dos veces seguidas)
5. Copiar el directorio `src/main/java/img` a `target/classes/img`.
