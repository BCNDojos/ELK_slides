<!-- background: #fff -->
<!-- color: #000 -->
<!-- font: frutiger -->

## Logstash

**- ¿Qué es Logstash?**
 És una aplicación JRuby de tratamiento de logs que permite recolectar, centralizar, parsear,   guardar y extraer datos, mediante el uso de plugins podemos trabajar con distintos sistemas de envio de logs, varios tipos de procesado y modificación de logs, varias soluciones de almacenamiento de datos análisis y visualización.


**- ¿ Cómo funciona?**
Consta de un proceso corriendo en todos nuestros servidores que envia los logs a un Redis para centralizar toda la información, para el envio se pueden usar varias soluciones como RSyslog, Logstash Agent, Syslogd, Syslog-NG. Posteriormente un proceso de Logstash los recoje/modifica los logs como le hayamos dicho para mandarlos finalmente a Elasticsearch. 

**- ¿Qué hace?**
Recoge todos los logs de una serie de entradas para filtrarlos, modificarlos, añadirles tags, hacer match de expresiones regulares/filtros GROK, limpizar logs, crear checksums para deduplicación de eventos, extraer pares de clave/valor, realizar descubrimento Geoip y DNS para control de fraude, monitorizar rangos de datos en campos para alertas, separar en distintos eventos un mensaje y anonimizar datos. Todos estos filtros pueden usarse aplicando unas reglas de lógica que nos permiten un sinfín de posibilidades como anonimizar unos logs para su uso en el entorno de test mientras se les aplica con otro filtro una modificación de los campos y añadido de tags para que la linea tenga los datos separados y etiquetas que habremos definido nosotros que posteriormente podemos usar para crear un Dashboard en Kibana donde se muestra que los nuevos usuarios IOS han sido un 20% mas altas en Enero que en Diciembre y que el ratio de errores en estos ha bajado un 3%,  todo esto con un mapa que nos muestra que tanto por ciento por país corresponde a estas cifras usando la localización por GeoIP.
