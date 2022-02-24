# clever-challenge

Ejercicio 1)

Casos de prueba para la API de temperaturas

Algunas consideraciones que tome de acuerdo a lo que decia el texto del ejercicio:
- La request seria del tipo https://api-weather.com/01-01-1999 por ejemplo
- Se omitieron algunos casos para no ser reiterativos y redundantes ante algunas combinaciones de ciudad y pais pero si fuera un caso de la vida real serian     incluidos.
- El texto no lo aclara pero supongo que la api soporta fechas anteriores a la actual como validas tambien.
- Los casos de prueba se encuentran en: https://docs.google.com/spreadsheets/d/1WxJHDXI-cS0TVsqN0PbDGd90S_FVXAksrptgqKH7FyU/edit?usp=sharing


Ejercicio 2)

La automatizacion de los fierentes casos de prueba para la api se encuentran dentro de la carpeta collections. En la carpeta environment se encuentran tambien las variables usadas para alguno de los casos.


Ejercicio 3)

Tanto para la generacion de los casos de prueba realizados en el punto 1 y la automatizacion realizada en el punto 2, se utilizaron las tecnicas conocidas como "happy path" o el camino "feliz" para generar los primeros casos que son todos los flujos correctos en los cuelaes deberia responder correctamente la api. Y luego se prosiguio con el "negative path" o "negative testing" que serian todos los casos negativos que se desprenden del flujo normal o "feliz". Para los ultimos casos se aplicaron tecnicas de monkey testing en el sentido que se generaron casos con combinaciones de headers que no tenian sentido o combinaciones inverosimiles para poner a prueba la aplicacion bajo esas circunstancias.
En los casos que se probaban con combinaciones de mayusculas y minusculas se hace uso de la tecnica "border testing" que es ir probando con valores cercanos al limite que permite aplicacion para ver si se encuentra un punto de falla "borde" no contemplado, en este caso es cuando probamos los headers con diferentes combinaciones de mayusculas o minusculas.

En cuanto a los puntos a tener en cuentas o buenas practicas para probar apis puedo nombrar algunos que me resultaron utiles:
- Entender bien los requermientos que se piden y ver en que parte del flujo de la aplicacion entra en juego la api, eso ayuda mucho a imaginarse posibles escenarios de prueba y dar un poco mas de contexto a las pruebas.
- No validar solo status de exito o 200, sino que explorar todas las opciones para ver si las respuestas que nos va a arrojando la api se adaptan a los estandares de codigos http que se usan o hay alguna discrepancia.
- No probar mas de una api en el mismo test, muchas veces es tentador para probar algun flujo en particular usar varios endpoints diferentes para realizar una prueba integral pero no es lo recomendable, por lo general conviene agrupar los casos y pruebas para cada endpoint particular y no mezclar condiciones. Esto lleva a una mejor organizacion y eficiencia a la hora de organizar el trabajo.
- Siempre utilizar los metodos de testing postivo y negativo para divisar rapidamente cuales son los casos principales a chequear.
- Si estamos automatizando pruebas de apis, tratar de reusar los datos a utilizar en las requests y hacer uso de arcivos externos tales como csv, json, etc para utilizarlos despues direcxtamente en el codigo sin tener que repetir variables todo el tiempo. De esta forma se escribe menos codigo y se emprolija la forma de realizar los tests, ademas de que se gana tiempo en el desarrollo y evita posibles futuras fallas.
