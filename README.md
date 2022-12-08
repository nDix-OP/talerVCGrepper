# Taller de Visual Code Grepper

Taller realizado por Iván Ortiz del Noval, Marcos Fernández Alonso e Irene Zamanillo Zubizarreta sobre la herramienta
Visual Code Grepper. Tiene una duración estimada de 30 minutos, incluyendo la presentación y la resolución guiada del
ejercicio planteado.


## Enlaces importantes de VC Grepper
Instalación de VC Grepper: https://sourceforge.net/projects/visualcodegrepp/
Repositorio público de VC Grepper en GitHub: https://github.com/nccgroup/VCG

## Código de ejemplo
Código de ejemplo de una aplicación Java mal hecha: https://github.com/framaz/The_Game_No_Name 


## Ejercicio guiado

*Imagen para seleccionar el directorio (File -> New Target Directory):
![image](https://user-images.githubusercontent.com/80198607/206561947-ddc776c2-c40c-428c-8c24-c35410cf795b.png)

## Ejercicio guiado
## Configuración Personalizada
VisualCode Greeper cuenta con ciertas funciones, librerías, funciones OWASP etc que son consideradas como peligrosas, pero que ocurre si nosotros conocemos alguna que no este o simplemente queremos comprobar si están incluidas en las bases del programa. VisualCode Greeper cuenta con una serie de archivos que podemos inspeccionar e incluso editar en los cuales se incluyen las funciones, librerías etc que considera peligrosas y nos permite añadir las nuestras propias.
Para ello:

1.	Abrimos el programa y clicamos en “settings”
 ![image](https://user-images.githubusercontent.com/105552988/206568797-ae79ed74-0404-4f71-8c4f-e0709c38f044.png)
 
2.	A continuación, podemos darle a Banned/Insecure Functions… lo cual nos permite ver un archivo que contiene todo aquello considerado como inseguro/peligroso
 ![image](https://user-images.githubusercontent.com/105552988/206568839-72c5ba1c-ae48-45d0-9073-3f41f7c13413.png)
 
3.	Esto es lo que nos permite ver, si prestamos atención al nombre del fichero vemos que se llama “javafunctions.conf” esto se debe a que nuestro lenguaje seleccionado es Java. Realizad la prueba con c/c++ seleccionado

4.	Otra forma de visualizar este archivo es clicando en el botón de “Options”
![image](https://user-images.githubusercontent.com/105552988/206568856-3818ca0c-db2c-4b6f-8d78-f3165ef60987.png)
![image](https://user-images.githubusercontent.com/105552988/206568904-3ad7e9fa-c3e9-48e0-a28c-979c2f55945e.png) 

5.	Ahora vamos a la pestaña "Config Files". En este menú encontramos todos los archivos predefinidos con las funciones prohibidas / peligrosas consideradas por el programa. Aquí podemos editarlos para añadir nuestras propias funciones o directamente nuestro propio archivo.

6.	Vamos a probar a añadir una función al fichero de java y ver si salen errores.

7.	Damos a edit en la linea de Java:
![image](https://user-images.githubusercontent.com/105552988/206569065-7ab6dd18-7c4a-4442-85aa-d53b22d3631f.png)

8.  Añadimos las funciones personalizadas siguiendo el formato estipulado por VC Greeper, en este caso, primero ponemos el string que consideramos peligroso después lo seguimos de “=>” y entre corchetes “[1-3]” ponemos un valor del 1 al 3 para establecer su peligrosidad, si no ponemos nada se considera normal.  
![image](https://user-images.githubusercontent.com/105552988/206569615-f655d3b7-35ed-4931-9f72-d5aff738edf6.png)

9.  Una vez escritas las guardamos en un directorio que consideremos apropiado con un nombre que nos ayude a identificarlas.
10.   Corremos un scan general con los filtros para que solo salgan los errores médium y high que son el nivel de las funciones añadidas. Esto se ha enseñado anteriormente. Obtenemos los siguientes resultados:
 ![image](https://user-images.githubusercontent.com/105552988/206569090-31eb505d-5d96-4dfd-9906-962df62b8489.png)

11.  Como podemos ver aparecen las funciones añadidas.

