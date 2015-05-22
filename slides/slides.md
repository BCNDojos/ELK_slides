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
## Motivaciones
]
.right-column[

## Recolectar registros

- Desde distintos orígenes: ficheros, flujos, sistema, ...
- Pretratamiento
- Clasificación inicial
- Encaminamiento a distintos destinos

]
---
# Introducción
.left-column[
## Motivaciones
]
.right-column[

### Recolectar registros
## Tratamiento de los datos

- 

]
---
# Introducción
.left-column[
## Motivaciones
]
.right-column[

### Recolectar registros
### Tratamiento de los datos
## Análisis

- 

]
---
# Introducción
.left-column[
## Motivaciones
]
.right-column[

### Recolectar registros
### Tratamiento de los datos
### Análisis
## Visualización

- 

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

## Syslog

- **Estándar de facto**, definido en [RFC3164](https://www.ietf.org/rfc/rfc3164.txt)
- **Diferentes implementaciones existentes** en la mayoría de sistemas UN*X
- Comunicación por **protocolo UDP** (puerto 514)
- Desarrollado por [Eric Allman](http://en.wikipedia.org/wiki/Eric_Allman) para [Sendmail](http://en.wikipedia.org/wiki/Sendmail)
- Permite dos tipos de categorizaciones:
  + **Facility**: Indica el tipo de aplicación que hace el registro. Hay 24 tipos distintos.
  + **Severity**: Se refiere a la gravedad del evento registrado. Hay 8 tipos diferentes.
- Observaciones:
  + **Baja confiabilidad**: El protocolo UDP permite pérdida y no garantiza el orden de los mensajes.
  + **Falta de mecanismos de autenticación**: No hay mecanismos de autenticación en ningún sentido.
  + **Poca uniformidad**: Los procesos, aplicaciones y sistemas pueden hacer variar el formato del mensaje.
  + **Falta de herramientas**: No incluye herramientas de análisis ni tratamiento.

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
## Fluentd

- **Colector de logs**
- Permite distintos orígenes y destinos
- Incluye la posibilidad de filtrar, regular y dirigir mensajes
- Internamente, convierte los mensajes en documentos JSON
- Tiene posibilidad de conectar plugins
- Hecho en C y Ruby
- Observaciones:
  + **Poco conocido**: Aunque es relativamente conocido en la comunidad Ruby, no lo es mucho fuera de ella.
  + **Sustituto de Logstask**: Existe algo de información sobre cómo pasar de ELK a EFK.

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
### Fluentd
## Flume

- Otro **colector de logs**, pero distribuido.
- Envía los logs a Hadoop.
- Observaciones:
  + **Poco conocido**: Aún menos conocido que Fluentd, posiblemente más reconocido en entornos con Hadoop.

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
### Fluentd
### Flume
## Splunk

- Plataforma similar a ELK, pero bastante anterior.
- Sólo tiene licencia comercial.
- Observaciones:
  + **Conocimiento**: Aunque es bastante conocido, no parece que haya muchos usuarios.

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

]
---
## Logstash

**- ¿Qué es Logstash?**
 Es una aplicación JRuby de tratamiento de logs que permite recolectar, centralizar, parsear,   guardar y extraer datos, mediante el uso de plugins podemos trabajar con distintos sistemas de envio de logs, varios tipos de procesado y modificación de logs, varias soluciones de almacenamiento de datos análisis y visualización.


**- ¿ Cómo funciona?**
Consta de un proceso corriendo en todos nuestros servidores que envia los logs a un Redis para centralizar toda la información, para el envio se pueden usar varias soluciones como RSyslog, Logstash Agent, Syslogd, Syslog-NG. Posteriormente un proceso de Logstash los recoje/modifica los logs como le hayamos dicho para mandarlos finalmente a Elasticsearch. 
--
**- ¿Qué hace?**
Recoge todos los logs de una serie de entradas para filtrarlos, modificarlos, añadirles tags, hacer match de expresiones regulares/filtros GROK, limpiar logs, crear checksums para deduplicación de eventos, extraer pares de clave/valor, realizar descubrimento Geoip y DNS, monitorizar rangos de datos en campos para alertas, separar en distintos eventos de un mensaje y anonimizar datos. Todos estos filtros pueden usarse aplicando unas reglas de lógica que nos permiten un sinfín de posibilidades como anonimizar unos logs para su uso en el entorno de test mientras se les aplica con otro filtro una modificación de los campos y añadido de tags para que la linea tenga los datos separados y las etiquetas que habremos definido nosotros para posteriormente crear un Dashboard en Kibana donde se muestra que los nuevos usuarios IOS han sido un 20% mas altos en Enero que en Diciembre y que el ratio de errores en estos ha bajado un 3%, todo esto acompañado de mapa que nos muestra que tanto por ciento corresponde a cada pais usando la localización por GeoIP.
