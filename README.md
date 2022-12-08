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

## Análisis con filtrado
Al estar analizando la seguridad de una aplicación completa, el número de posibles brechas de seguridad que encontramos en el código es muy alto. Así que, partiendo del análisis realizado en el ejercicio 1, vamos a comprobar las distintas opciones de filtrado y búsqueda que nos ofrece VCGrepper.

En primer lugar, nos desplazamos a la sección Summary Table. Aquí aparece la lista completa de errores que se han encontrado en el código de la carpeta que estemos analizando. 

Como primera opción podemos ordenar el listado completo de errores en todos los archivos clicando sobre la opción Severity. Los valores más bajos (6, 7) corresponden a los errores de mayor severidad mientras que aquellos más altos representan aquellos menos importantes, sospechosos o cuyo potencial como amenaza no está claro del todo (1, 2, 3).

![imagen](https://user-images.githubusercontent.com/91279004/206575208-e9123dd5-f8ca-46a1-8a4f-6b6bdbfaaa37.png)

De igual forma, clicando sobre la opción FileName podemos ver los errores agrupados por su respectivo archivo.

Tras ordenar los errores, obtenemos una lista de errores ordenada por su severidad y en función del archivo al que pertenecen.

![imagen](https://user-images.githubusercontent.com/91279004/206575334-9c05c904-fca2-4db1-bb40-2e457efa6faa.png)

VCGrepper también nos permite filtrar estos resultados para, por ejemplo, ver solo los errores de una cierta severidad. Para ello hacemos *click derecho -> Filter Results*.
Se muestra la siguiente ventana emergente, en la que podemos filtrar los errores de 3 formas distintas:

- Display Results Equals to Or Above: muestra los errores iguales o de mayor severidad que el seleccionado.
- Display Results  Equals to Or Below: muestra los errores iguales o de menor severidad que el seleccionado.
- Display Results in the Range: muestra los errores en el rango de severidad indicado.

![imagen](https://user-images.githubusercontent.com/91279004/206575446-0e525554-1415-4733-a907-b789b69b7ac2.png)

Para comprobar solo los errores de mayor severidad (Critical y High) seleccionaremos *Equal to or Above: High*, de forma que muestre un único error.

![imagen](https://user-images.githubusercontent.com/91279004/206575536-536aefb7-88b5-4414-9968-b2bb3e75e85d.png)

Si queremos guardar estos resultados finales filtrados, haremos *click derecho -> Export Filtered XML Results*. En la ventana emergente, es necesario indicar un nombre para el fichero a exportar y una ruta.

Este mismo fichero puede ser reimportado en VCGrepper a través de la opción *File -> Import Results from XML File*

![imagen](https://user-images.githubusercontent.com/91279004/206575767-2d9b6f2b-f36f-44c6-9a8e-a76554be18fd.png)



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

