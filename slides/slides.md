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

- Extracción de datos
- Transformación de tipos
- Etiquetado de los registros
- Creación de nuevos datos según otros presentes
- Uso de expresiones regulares para el *parsing*

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

- Indexación para búsquedas
- Agregación
- Clasificación
- Correlación

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

- Búsqueda
- Selección
- Vista en directo
- Graficación

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

- Otro **colector de logs**, pero distribuido
- Envía los logs a Hadoop
- Observaciones:
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
### Fluentd
### Flume
## Splunk

- Plataforma similar a ELK, pero bastante anterior
- Sólo tiene licencia comercial
- Observaciones:
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
### Fluentd
### Flume
### Splunk
## SaaS (Loggly, Papertrail, Logentries, Sentry)

- Servicios online
- Tráfico máximo y rentención limitados y relativos al precio
- Información sensible en sistemas externos
- Algunos casos requieren tener agentes o enviar desde la aplicación directamente

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

## Elasticsearch

- Motor de indexación y búsqueda orientado a documento
- Escrito en Java
- API REST basada en JSON
- Funcionalidades analíticas
- Sin esquema
- Uso de plugins para ampliar funcionalidades
- Disponibilidad

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### Elasticsearch
## Logstash

- Recocopila registros de los eventos que se quieren registrar
- Múltiple fuentes de tipos distintos
- Preprocesado y normalización
- Transporte hasta uno o más destinos finales
- Capacidad de encaminamiento
- Escrito en JRuby
- Entradas, salidas, codecs y filtros ampliables mediante plugins

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### Elasticsearch
### Logstash
## Kibana

- Panel de control para búsquedas y análisis sobre ElasticSearch
- Muy sencillo
- Escrito en NodeJS
- Democratización del acceso a los datos
- Permite generar histogramas, análisis de términos, mapas, tablas,...
- Muy simple y bastante eficiente

]
---
# Introducción
.left-column[
### Motivaciones
### Otras Soluciones
## Descripción
]
.right-column[

### Elasticsearch
### Logstash
### Kibana
## Otros componentes

- Logstash-forwarder
- Beaver
- Woodchuck
- Redis

]
---
# Logstash

.left-column[
##¿Qué es Logstash?
]
.right-column[
Es una aplicación JRuby de tratamiento de logs que permite:

- Recolectar
- Centralizar
- Parsear/Modificar
- Enviar a un storage
]
---
# Logstash

.left-column[
##¿Qué es Logstash?
]
.right-column[
Es una aplicación JRuby de tratamiento de logs que permite:

- Recolectar
- Centralizar
- Parsear/Modificar
- Enviar a un storage

Mediante el uso de plugins podemos trabajar con:

- Distintos sistemas de envio de logs 
	- Syslogd
	- RSyslog 
	- RSyslog-NG
	- Logstash agent
	- Lumberjack
	- Logstash-forwareder
	- Snare for Widnows
	- KiwiSyslog
	- Syslog-Win32
	- ...
]
---
# Logstash

.left-column[
##¿Qué es Logstash?
]
.right-column[
Es una aplicación JRuby de tratamiento de logs que permite:

- Recolectar
- Centralizar
- Parsear/Modificar
- Enviar a un storage

Mediante el uso de plugins podemos trabajar con:

- Distintos sistemas de envio de logs 
- Varios tipos de procesado y modificacion de logs
	- Parseado
	- Mutación
	- Limpieza
	- Añadido de campos
	- Geolocalización
	- ...
]
---
# Logstash

.left-column[
##¿Qué es Logstash?
]
.right-column[
Es una aplicación JRuby de tratamiento de logs que permite:

- Recolectar
- Centralizar
- Parsear/Modificar
- Enviar a un storage

Mediante el uso de plugins podemos trabajar con:

- Distintos sistemas de envio de logs 
- Varios tipos de procesado y modificacion de logs
- Varias soluciones de almacenamiento/salida de datos
	- Almacenamiendo en Elasticsearch
	- Envio de mails según lógica y filtros preestablecidos
	- 