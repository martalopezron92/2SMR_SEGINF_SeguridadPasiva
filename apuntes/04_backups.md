
# Backup de datos

## ¿Qué es un backup?
Un backup (o copia de seguridad) es una duplicación de los datos que se realiza para poder recuperarlos en caso de que se pierdan o sufran daños. La finalidad de un backup es proteger la información crítica y minimizar las interrupciones en caso de un fallo del sistema, ataque de virus, corrupción de datos o errores de usuario.

* Se realiza de forma periódica.
* Hay diferentes tipos de copias de seguridad (completas, incrementales, diferenciales...).
* Mantener copias de los datos en lugares distintos (por ejemplo, otra máquina o un servicio en la nube) reduce el riesgo de pérdida total.

## Herramientas de gestión de eventos (logs)
Los logs (archivos de registro) son ficheros de texto donde los sistemas y aplicaciones dejan constancia de todo lo que ocurre: operaciones realizadas, errores, advertencias, etc. Para analizar y gestionar estos logs, existen varias herramientas muy populares en sistemas operativos tipo Unix/Linux. Veamos algunas:

### Awk

* Awk es un lenguaje de programación y herramienta de procesamiento de texto muy potente. Se utiliza, sobre todo, para la búsqueda de patrones y el procesamiento de archivos de texto, especialmente logs.
* Permite procesar cada línea de un archivo, dividiéndola en campos, y realizar acciones (imprimir, sumar, reemplazar…).
* Uso habitual:
```
awk '/ERROR/ {print $0}' archivo.log
```
En este ejemplo, se muestran todas las líneas que contengan la palabra "ERROR" en el archivo archivo.log.

### Grep

* Grep es una herramienta de línea de comandos que busca patrones de texto dentro de archivos.
* Filtra línea a línea y muestra únicamente las líneas que cumplan con el patrón buscado.
* Uso habitual:
```
grep "ERROR" archivo.log
```
Muestra las líneas que contienen la palabra “ERROR” en archivo.log.

### Sed

* Sed es un editor de flujo (stream editor) muy potente que se usa para buscar y reemplazar texto de forma automática en archivos, así como para extraer y analizar datos.
* Aplica un conjunto de instrucciones a cada línea de un archivo.
* Uso habitual: Reemplazar la palabra “ERROR” por “ERR” en todas las líneas:
```
sed 's/ERROR/ERR/g' archivo.log
```
Donde s significa “sustituir” (substitute), “ERROR” es el patrón y “ERR” el texto a reemplazar. La g indica que se aplique a todas las ocurrencias de la línea.

### Syslog / Rsyslog

* Son sistemas de registro (logging) muy utilizados en Linux/Unix. Syslog es el sistema de logging tradicional; Rsyslog es una versión más moderna y avanzada, que permite mayor velocidad y más opciones de configuración.
* Recopilan logs provenientes de múltiples fuentes (el propio sistema operativo, servicios, aplicaciones…) y centralizan toda esa información en uno o varios archivos de log, o incluso en un servidor remoto.
* Uso habitual:
    * Configurar la recogida de logs del sistema en rsyslog.conf.
    * Enviar logs a un servidor remoto para su análisis.
    * Centralizar registros en un solo punto, lo cual facilita la monitorización y la auditoría.

## Herramientas de backup
Existen distintas herramientas de copia de seguridad, cada una con sus ventajas. Algunas son más sencillas y manuales, mientras que otras ofrecen sistemas de administración más complejos y automatizaciones.

### Rsync

* Es una herramienta de sincronización y copia de archivos muy popular en Linux/Unix.
* Características principales:
    * Solo transfiere los archivos (o partes de archivos) que han cambiado, lo que ahorra ancho de banda y tiempo.
    * Permite hacer copias locales o remotas, usando un servidor.
* Ejemplo de uso:
```
rsync -avz /ruta/origen/ usuario@servidor:/ruta/destino/
```
*  -a (archive): mantiene permisos, dueños, fechas, etc.
*  -v (verbose): muestra lo que se está copiando.
* -z (compress): comprime la información durante la transferencia.

### Bacula
* Es un sistema de copia de seguridad cliente-servidor que permite gestionar grandes infraestructuras de manera centralizada.
* Características principales:
    * Dispone de consola web para monitorizar y configurar las copias de seguridad.
    * Automatiza y programa backups completos, incrementales o diferenciales.
    * Permite restauraciones granulares (desde un solo archivo hasta un sistema completo).

### UrBackup
* Es un sistema de backup que combina un cliente (instalado en cada ordenador que se quiera respaldar) con un servidor que recibe y almacena las copias.
* Características principales:
    * Fácil de configurar a nivel de red local.
    * Ofrece copias de seguridad de archivos e imágenes de disco.
    * Interfaz web para gestionar y supervisar los backups de todos los clientes.

### Cronopete
* Es una solución de backup para sistemas tipo Linux inspirada en “Time Machine” de macOS.
* Características principales:
    * Realiza copias de seguridad incrementales de los archivos cada cierto intervalo de tiempo.
    * Permite recuperar versiones anteriores de archivos de forma sencilla.
    * Ideal para usuarios que buscan una solución similar a Time Machine en Linux.


## Preguntas relacionadas

### ¿Qué es un cluster?

Un cluster es un conjunto de equipos (servidores o nodos) que trabajan juntos para proporcionar un servicio como si fueran un solo sistema.

* Objetivos:
    * Mejorar la disponibilidad (si un nodo falla, los demás siguen funcionando).
    * Incrementar la capacidad de procesamiento (varios nodos comparten la carga).
    * Facilitar la escalabilidad (se pueden añadir más nodos según las necesidades).

* Ejemplos:
    * Clusters de bases de datos (varios servidores comparten la carga de consultas).
    * Clusters de cómputo (muchos nodos procesan grandes volúmenes de datos simultáneamente).

### ¿Qué es la alta disponibilidad?

La alta disponibilidad (High Availability, HA) consiste en diseñar sistemas de forma que el servicio esté disponible el mayor tiempo posible. Habitualmente, se busca un tiempo de inactividad mínimo, cercano a cero.

* Cómo se consigue:
    * Redundancia de componentes (discos, tarjetas de red, fuentes de alimentación).
    * Uso de clusters y técnicas de conmutación por error (failover).
    * Replicación de datos y monitorización constante.

* Ejemplo: Un sitio web de venta online que no puede permitirse caer, ya que cada minuto sin servicio implica pérdidas económicas. Se utilizan servidores redundantes de forma que, si uno falla, otro toma el relevo sin interrumpir el servicio.

### ¿Qué es la alta confiabilidad?

La alta confiabilidad (o alta fiabilidad) se refiere a que el sistema en su conjunto rara vez falla o experimenta errores.

* Diferencia con la alta disponibilidad:
    * **Alta disponibilidad:** el servicio se mantiene operativo incluso si hay fallos de componentes (está más enfocada al tiempo en funcionamiento).
    * **Alta confiabilidad:** el sistema está diseñado para minimizar la probabilidad de que se produzcan fallos (en lugar de recuperarse rápido, evita que ocurran fallos).

* Cómo se consigue: 
    * Con ingeniería de calidad, uso de hardware y software muy probado.
    * Diseñando sistemas tolerantes a fallos.
    
### ¿Qué es el alto rendimiento?

Se refiere a la capacidad de un sistema para procesar gran cantidad de datos o atender muchas solicitudes en un tiempo corto, ofreciendo una respuesta rápida.

* Ejemplo:
    * Servidores de aplicaciones que pueden manejar millones de peticiones diarias.
    * Sistemas de computación científica con miles de procesadores que realizan cálculos complejos a alta velocidad.

* Cómo se logra:
    * Usando hardware potente (procesadores multinúcleo, memorias rápidas, SSD, etc.).
    * Optimizando el software y la arquitectura (base de datos distribuida, uso de caché, etc.).
    * Realizando un buen diseño de red y balanceo de carga (ver siguiente apartado).

### ¿Qué es el balanceo de carga?
El balanceo de carga (load balancing) es una técnica que distribuye el tráfico o las peticiones entre múltiples servidores para evitar sobrecargas y mejorar la velocidad de respuesta.
* **Ejemplo:**Un servidor web que recibe muchas solicitudes de usuarios. En vez de que un solo servidor atienda todo el tráfico, se reparten las peticiones entre varios servidores web.
* **Ventajas:**
    * Mayor rendimiento (menos tiempo de respuesta).
    * Alta disponibilidad (si un servidor cae, el balanceador redirige el tráfico a otros activos).
* **Herramientas de ejemplo:** Nginx, HAProxy, entre otros.

### ¿Qué es un backup incremental?
Un backup incremental es una copia de seguridad que solo guarda los datos que han cambiado o se han añadido desde la última copia (ya sea la última copia completa o incremental).
* **Ventaja principal:** Se reducen drásticamente el tiempo y el espacio de almacenamiento necesarios, puesto que no se vuelven a copiar todos los datos una y otra vez.
* **Funcionamiento:**
Supongamos que el lunes hacemos un backup completo de todo.
El martes hacemos un backup incremental, que copia solo los cambios que hubo del lunes al martes.
El miércoles otro incremental, y así sucesivamente.
* **Consideraciones:**
Para restaurar el sistema completo, se necesita el backup completo inicial y todos los incrementales que se hayan hecho posteriormente.
Algunos sistemas optan por realizar backups completos periódicos (por ejemplo, una vez por semana) para simplificar la restauración.