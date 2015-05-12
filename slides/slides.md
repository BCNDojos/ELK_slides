title: ELK
description: Presentación sobre ELK.
name: inverse
layout: true
class: center, top, inverse
---
background-image: url(http://upload.wikimedia.org/wikipedia/commons/c/c7/Logs.jpg)

# ¿Qué haces tú con tus logs?
--

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
## - Josep Pla ([@joseppla74](https://twitter.com/joseppla74)): Ingeniero de sistemas en Upptalk
## - Ignasi Fosch ([@ifosch](https://twitter.com/ifosch)): Ingeniero de sistemas en Devex
---
layout: false
# Introducción
.left-column[
## Soluciones alternativas
]
.right-column[

  - Syslog
]
---
# Introducción
.left-column[
## Soluciones alternativas
]
.right-column[

  - Syslog

    + Demonio presente en la mayoría de sistemas UN*X
]
---
# Introducción
.left-column[
## Soluciones alternativas
]
.right-column[

  - Syslog

  - Splunk
]
---
# Introducción
.left-column[
## Soluciones alternativas
## Motivaciones
]
.right-column[

- Visualizar
- Centralizar
]
---
# Logstash

.left-column[
##¿Qué es Logstash?##

Es una aplicación JRuby de tratamiento de logs que permite:

-Recolectar
-Centralizar
-Parsear/Modificar
-Enviar a un storage

Mediante el uso de plugins podemos trabajar con distintos sistemas de envio de logs, varios tipos de procesado y modificación de logs, varias soluciones de almacenamiento de datos, análisis y visualización.
]
--
.right-column[
**- ¿ Cómo funciona?**
Consta de un proceso corriendo en todos nuestros servidores que envia los logs a un Redis para centralizar toda la información, para el envio se pueden usar varias soluciones como RSyslog, Logstash Agent, Syslogd, Syslog-NG. Posteriormente un proceso de Logstash los recoje/modifica los logs como le hayamos dicho para mandarlos finalmente a Elasticsearch. 
]
---
**- ¿Qué hace?**
Recoge todos los logs de una serie de entradas para filtrarlos, modificarlos, añadirles tags, hacer match de expresiones regulares/filtros GROK, limpiar logs, crear checksums para deduplicación de eventos, extraer pares de clave/valor, realizar descubrimento Geoip y DNS, monitorizar rangos de datos en campos para alertas, separar en distintos eventos de un mensaje y anonimizar datos. Todos estos filtros pueden usarse aplicando unas reglas de lógica que nos permiten un sinfín de posibilidades como anonimizar unos logs para su uso en el entorno de test mientras se les aplica con otro filtro una modificación de los campos y añadido de tags para que la linea tenga los datos separados y las etiquetas que habremos definido nosotros para posteriormente crear un Dashboard en Kibana donde se muestra que los nuevos usuarios IOS han sido un 20% mas altos en Enero que en Diciembre y que el ratio de errores en estos ha bajado un 3%, todo esto acompañado de mapa que nos muestra que tanto por ciento corresponde a cada pais usando la localización por GeoIP.
