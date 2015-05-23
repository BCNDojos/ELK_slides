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

- ####Desde distintos orígenes: ficheros, flujos, sistema, ...
- ####Pre-tratamiento
- ####Clasificación inicial
- ####Encaminamiento a distintos destinos

]
---
# Introducción
.left-column[
## Motivaciones
]
.right-column[

### Recolectar registros
## Tratamiento de los datos

- ####Extracción de datos
- ####Transformación de tipos
- ####Etiquetado de los registros
- ####Creación de nuevos datos según otros presentes
- ####Uso de expresiones regulares para el *parsing*

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

- ####Indexación para búsquedas
- ####Agregación
- ####Clasificación
- ####Correlación

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

- ####Búsqueda
- ####Selección
- ####Vista en directo
- ####Crear gráficas

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

## Syslog

- ####Desarrollado por [Eric Allman](http://en.wikipedia.org/wiki/Eric_Allman) para [Sendmail](http://en.wikipedia.org/wiki/Sendmail)
- ####**Estándar de facto**, definido en [RFC3164](https://www.ietf.org/rfc/rfc3164.txt)
- ####**Diferentes implementaciones existentes** en la mayoría de sistemas
- ####Permite dos tipos de categorizaciones:
  + **Facility**: Indica el tipo de aplicación que hace el registro. Hay 24 tipos distintos.
  + **Severity**: Se refiere a la gravedad del evento registrado. Hay 8 tipos diferentes.
- ####Observaciones:
  + **Baja confiabilidad**: El protocolo UDP permite pérdida y no garantiza el orden de los mensajes.
  + **Falta de herramientas**: No incluye herramientas de análisis ni tratamiento.
  + **Falta de mecanismos de autenticación**: No hay mecanismos de autenticación en ningún sentido.

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
## [Fluentd](http://www.fluentd.org/)

- ####**Colector de logs**
- ####Permite distintos orígenes y destinos
- ####Incluye la posibilidad de filtrar, regular y dirigir mensajes
- ####Internamente, convierte los mensajes en documentos JSON
- ####Tiene posibilidad de conectar *plugins*
- ####Hecho en C y Ruby
- ####Observaciones:
  + **Poco conocido**: Aunque es relativamente conocido en la comunidad Ruby, no lo es mucho fuera de ella.
  + **Sustituto de Logstash**: Existe algo de información sobre cómo pasar de ELK a EFK.

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
### [Fluentd](http://www.fluentd.org/)
## [Flume](https://flume.apache.org/)

- ####Otro **colector de logs**, pero distribuido
- ####Envía los logs a Hadoop
- ####Observaciones:
  + **Poco conocido**: Aún menos conocido que Fluentd, posiblemente más reconocido en entornos con Hadoop

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
### [Fluentd](http://www.fluentd.org/)
### [Flume](https://flume.apache.org/)
## [Splunk](http://www.splunk.com/)

- ####Plataforma similar a ELK, pero bastante anterior
- ####Sólo tiene licencia comercial
- ####Observaciones:
  + **Conocimiento**: Aunque es bastante conocido, no parece que haya muchos usuarios

]
---
# Introducción
.left-column[
### Motivaciones
## Otras Soluciones
]
.right-column[

### Syslog
### [Fluentd](http://www.fluentd.org/)
### [Flume](https://flume.apache.org/)
## [Splunk](http://www.splunk.com/)
## [Loggly](https://www.loggly.com/), [Papertrail](https://papertrailapp.com/), [Logentries](https://logentries.com/), [Sentry](https://getsentry.com/welcome/)

- ####Servicios en línea
- ####Tráfico máximo y retención limitados y relativos al precio
- ####Información sensible en sistemas externos
- ####Algunos casos requieren tener agentes o enviar desde la aplicación directamente

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

## [Elasticsearch](https://www.elastic.co/products/elasticsearch)

- ####Escrito en Java por [Shay Banon](https://twitter.com/kimchy)
- ####Motor de indexación y búsqueda orientado a documento
- ####Escrito en Java
- ####API REST basada en JSON
- ####Funcionalidades analíticas
- ####Sin esquema
- ####Uso de *plugins* para ampliar funcionalidades
- ####Disponibilidad

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### [Elasticsearch](https://www.elastic.co/products/elasticsearch)
## [Logstash](https://www.elastic.co/products/logstash)

- ####Escrito en JRuby por [Jordan Sissel](https://twitter.com/jordansissel)
- ####Recopila registros de los eventos
- ####Múltiples fuentes de tipos distintos
- ####Pre-procesado y normalización de los datos
- ####Transporte hasta uno o más destinos finales
- ####Capacidad de encaminamiento
- ####Entradas, salidas, *codecs* y filtros ampliables mediante *plugins*

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### [Elasticsearch](https://www.elastic.co/products/elasticsearch)
### [Logstash](https://www.elastic.co/products/logstash)
## [Kibana](https://www.elastic.co/products/kibana)

- ####Escrito en NodeJS
- ####Panel de control para búsquedas y análisis sobre ElasticSearch
- ####Muy sencillo
- ####Democratización del acceso a los datos
- ####Permite generar histogramas, análisis de términos, mapas, tablas,...
- ####Muy simple y bastante eficiente

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### [Elasticsearch](https://www.elastic.co/products/elasticsearch)
### [Logstash](https://www.elastic.co/products/logstash)
### [Kibana](https://www.elastic.co/products/kibana)
## Otros componentes

- #### [Logstash-forwarder](https://github.com/elastic/logstash-forwarder)
- #### [Beaver](http://beaver.readthedocs.org/en/latest/)
- #### [Woodchuck](https://github.com/danryan/woodchuck)
- #### [Redis](http://redis.io/)

]
---
# Logstash
.left-column[
##¿Qué es?
]
.right-column[
###Es una aplicación JRuby de tratamiento de logs que permite:

- ####Recolectar
- ####Centralizar
- ####Parsear/Modificar
- ####Enviar a una salida
]
---
# Logstash

.left-column[
##¿Qué es?
]
.right-column[
###Es una aplicación JRuby de tratamiento de logs que permite:
  - ####Recolectar, centralizar, parsear/modificar, enviar a una salida.

###Mediante el uso de plugins podemos trabajar con:

- ####Distintos sistemas de envio de logs 
	- Syslogd
	- RSyslog 
	- RSyslog-NG
	- Logstash agent
	- Logstash-forwarder
	- Snare for Windows
	- KiwiSyslog
	- Syslog-Win32
	- ...
]
---
# Logstash

.left-column[
##¿Qué es?
]
.right-column[
###Es una aplicación JRuby de tratamiento de logs que permite:
  - ####Recolectar, centralizar, parsear/modificar, enviar a una salida.

###Mediante el uso de plugins podemos trabajar con:

- ####Distintos sistemas de envio de logs 

- ####Varios tipos de procesado y modificacion de logs
	- Parseado
	- Mutación
	- Limpieza
	- Añadido de campos
	- Geolocalización
	- Deduplicación de eventos
	- ...
]
---
# Logstash

.left-column[
##¿Qué es?
]
.right-column[
###Es una aplicación JRuby de tratamiento de logs que permite:
  - ####Recolectar, centralizar, parsear/modificar, enviar a una salida.

###Mediante el uso de plugins podemos trabajar con:

- ####Distintos sistemas de envio de logs 

- ####Varios tipos de procesado y modificacion de logs

- ####Varias soluciones de almacenamiento/salida de datos
	- Almacenamiendo en Elasticsearch
	- Envio de mails según lógica y filtros preestablecidos
	- Envio de mensajes a través xmpp
	- Envio de alertas a Nagios
	- Creación de metricas usando StatsD
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash
- #### Shipper
	- Es el servicio que corre en cada maquina y se encarga de recoger los logs deseados, taggearlos y enviarlos a un "broker" o al servicio central de Logstash
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash
- #### Shipper
	- Es el servicio que corre en cada maquina y se encarga de recoger los logs deseados, taggearlos y enviarlos a un "broker" o al servicio central de Logstash
- #### Broker
	- Si lo tenemos, es el encargado de recoger todos los logs que envian los shippers para que posteriormente el Logstash central los coja para procesarlos
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash

- #### Shipper
	- Es el servicio que corre en cada maquina y se encarga de recoger los logs deseados, taggearlos y enviarlos a un "broker" o al servicio central de Logstash
- #### Broker
	- Si lo tenemos, es el encargado de recoger todos los logs que envian los shippers para que posteriormente el Logstash central los coja para procesarlos
- #### Logstash Central
	- Es el encargado de recoger todos los logs del broker o los agentes de logstash y aplicarles una logica definida por el usuario para modificarlos, parsearlos y enviar el resultado a una serie de salidas (Elasticsearch, Nagios, Mail, etc...)
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash

- #### Shipper
	- Es el servicio que corre en cada maquina y se encarga de recoger los logs deseados, taggearlos y enviarlos a un "broker" o al servicio central de Logstash
- #### Broker
	- Si lo tenemos, es el encargado de recoger todos los logs que envian los shippers para que posteriormente el Logstash central los coja para procesarlos
- #### Logstash Central
	- Es el encargado de recoger todos los logs del broker o los agentes de logstash y aplicarles una logica definida por el usuario para modificarlos, parsearlos y enviar el resultado a una serie de salidas (Elasticsearch, Nagios, Mail, etc...)

Algunos de estos componentes pueden estar en la misma maquina, pueden ser un mismo proceso realizando varios de los roles e incluso alguno puede no existir en nuestra instalación.
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash

- ####Shipper, Broker, Logstash Central

###Recolección

  Es la fase donde el agente recoge, etiqueta y reenvia los logs

  - Se definen una serie de entradas (inputs) en el fichero de configuración

  - Se aplican una serie de etiquetas a fin de que posteriormente sea mas sencillo aplicar la lógica y filtros deseados
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash

 - ####Shipper, Broker, Logstash Central

###Recolección

###Tratamiento

  Es la fase en que parseamos, modificamos, añadimos datos

  - Se aplican una serie de filtros según una lógica que definimos en el fichero de configuración que nos permiten realizar todas las modificaciones citadas anteriormente
]
---
# Logstash

.left-column[
###¿Qué es?
##¿Cómo Funciona?
]
.right-column[
### Arquitectura del sistema Logstash

 - ####Shipper, Broker, Logstash Central

###Recolección

###Tratamiento

###Envio  

  Es la fase en que enviamos los datos procesados
 
 - Se definen una serie de salidas (outputs) en el fichero de configuración

 - Podemos definir una lógica que aplique filtros de salida para que según el tipo de datos o etiquetas que hayamos añadido estos se envien a distintos destinos y en distintos formatos
]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

### Motor de indexación

- ####Sistema que recibe datos y los ordena
- ####Basado en [Apache Lucene](https://lucene.apache.org/core/), escrito en Java por [Doug Cutting](https://twitter.com/cutting) en 1999
- ####Los datos se almacenan en índices
- ####Se pueden realizar análisis de diferentes tipos

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
### Orientado a documento

- ####Los datos están organizados en documentos
- ####Formato JSON
- ####Mantiene la copia original y la versión de cada documento

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
#### Orientado a documento
### Esquema dinámico

- ####La definición de la estructura de los documentos es opcional
- ####Se pueden definir algunos o todos los campos de los documentos
- ####La estructura de los documentos puede cambiar
- ####Si falta un campo solicitado, se muestra como no existente

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
#### Orientado a documento
#### Esquema dinámico
### Motor de búsqueda

- ####Realizar búsquedas sobre los datos indexados
- ####Uso de filtros sobre las búsquedas
- ####Uso de parámetros sobre los datos, sus estadísticas, ...
- ####Permite obtener facetas de las búsquedas

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
#### Orientado a documento
#### Esquema dinámico
#### Motor de búsqueda
### API REST basada en JSON

- ####La comunicación se realiza mediante una API REST HTTP
- ####Los mensajes, tanto de petición como de respuesta, son JSON

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
#### Orientado a documento
#### Esquema dinámico
#### Motor de búsqueda
#### API REST basada en JSON
### Funcionalidades analíticas

- ####Estadísticas: Media, máximo, mínimo, suma, percentiles,...
- ####Análisis de términos
- ####Rangos numéricos, de fecha, de IP
- ####Cálculo de distancias geográficas
- ####Generación de histogramas

]
---
# ElasticSearch
.left-column[
## ¿Qué es?
]
.right-column[

#### Motor de indexación
#### Orientado a documento
#### Esquema dinámico
#### Motor de búsqueda
#### API REST basada en JSON
#### Funcionalidades analíticas
### Disponibilidad

- ####Distribuido entre varios nodos
- ####Permite descubrimiento de nodos
- ####Realiza *sharding* entre los nodos de forma automática
- ####Distribuye la carga de las consultas entre los nodos presentes

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

### Instalación

- Descargar de ElasticSearch (Comprimido o empaquetado)
- Único requerimiento: Java (versión reciente)
- 1 fichero de configuración = 1 proceso = 1 nodo
- Nodos agrupados en un *cluster* definido por nombre
- Uno de los nodos se comporta como maestro
- El maestro es elegido y promovido dinámicamente
- Un nuevo nodo descubre a los otros del *cluster* automáticamente

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

#### Instalación
### Interfaz

- La interfaz es una API REST HTTP basada en JSON
- Los comandos HTTP definen el tipo de acción (GET, PUT, ...)
- La operación a ejecutar se determina por la URL solicitada
- La información enviada, en formato JSON, en el cuerpo de la petición

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

#### Instalación
#### Interfaz
### Indices

- Los índices se dividen físicamente en *primary shards*, por defecto 5
- Cada documento se escribe en un sólo *primary shard*
- La cantidad de documentos escala con la cantidad de *primary shards*
- Cada *primary shard* puede tener 0 o más réplicas
- La cantidad de réplicas escalará la disponibilidad y rendimiento
- Los índices se dividen lógicamente en tipos
- *Percolator*: Según consultas asociadas al índice, visualiza indexaciones coincidentes

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

#### Instalación
#### Interfaz
#### Indices
### Esquema

- Es opcional
- ElasticSearch adivinará los tipos de datos, con cierto margen de error
- El esquema se define con *mappings*
- Se definen propiedades para cada campo del documento
- Las propiedades definen lo que se hará, y cómo, con cada campo

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

#### Instalación
#### Interfaz
#### Indices
#### Esquema
### Análisis

- Según se defina en el esquema, se realizarán unos u otros análisis sobre los datos
- Textual: Dependen del idioma
  + *Tokenization*: Identificar palabras
  + *Stemming*: Identificar significado
  + Filtrado: Identificar y eliminar palabras vacías y elementos de formato
- Espacial:
  + Dependiente de la geografía
  + Distancias, polígonos
- Otros posibles: Fecha, hora, importe, ...
- Puntuación de relevancia
- Se puede probar el análisis con la API

]
---
# ElasticSearch
.left-column[
### ¿Qué es?
## ¿Cómo funciona?
]
.right-column[

#### Instalación
#### Interfaz
#### Indices
#### Esquema
#### Análisis
### Indexación y búsqueda

- Indexa documentos en masa con altas tasas de escritura
- Las búsquedas pueden ser de diferentes tipos y filtradas
- Incorpora uso de facetas y puntuación de relevancia en las búsquedas

]
---
# Kibana

.left-column[
##¿Qué es?
]
.right-column[

### Una aplicación NodeJS (v4) para visualización, creacion y gestión de las consultas que se lanzan contra Elasticsearch.
]
---
# Kibana

.left-column[
###¿Qué es?
##¿Qué hace?
]
.right-column[
###Ofrece una interfaz gráfica para:

  - ####Consultar y visualizar eventos de log

  - ####Filtrar y agregar datos

  - ####Generar representaciones gráficas de dichos datos (lineas, columnas, pastel, mapa,métrica, etc...)

  - ####Generar cuadros de mando agrupando graficos y visualizaciones
]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
## Detalles
]
.right-column[
### Tres entornos: develop, master y producción

]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
## Detalles
]
.right-column[
#### Tres entornos: develop, master y producción
### Actualmente, sólo en uso para develop y master

]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
### Detalles
## Arquitectura
]
.right-column[
### Logstash

- Instalado en cada servidor
- Lee de varios ficheros: syslog, errores, acceso, aplicación, ...
- Realiza el pre-tratamiento
- Envía a un syslog y a un ElasticSearch
- Para cada fichero y día utiliza índices distintos

]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
### Detalles
## Arquitectura
]
.right-column[
#### Logstash
### ElasticSearch y Kibana

- Un cluster con un sólo nodo
- Kibana instalado en el mismo servidor

]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
### Detalles
### Arquitectura
## Casos de uso
]
.right-column[

### Visualización de eventos en tiempo (casi) real

]
---
# Instalación en [Devex](https://www.devex.com/)

.left-column[
### Detalles
### Arquitectura
## Casos de uso
]
.right-column[

#### Visualización de eventos en tiempo (casi) real
### Detección de errores

]
---
# Instalación en Upptalk

.left-column[
]
.right-column[
]
