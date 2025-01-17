Introducción[](#introducción)
-----------------------------

En el diseño, planificación e implantación de un centro de procesos de datos se debe tener presente dónde se va a implantar, el suministro eléctrico, cómo se distribuye, se protege y se mantiene, las condiciones ambientales óptimas para el personal y para el control de elementos que se calientan, los sistemas de detección de incendios e inundaciones, la ubicación y distribución de los grandes armarios y servidores blade y el cableado estructurado, y los sistemas de videovigilancia y control de acceso.

![Protección física del CPD](https://marcosruiz.github.io/assets/img/que-es-un-cpd/proteccionFisicaCpd.png) _Protección física del CPD_

¿Qué es un CPD?
-------------------------------------------

Las empresas colocan los equipos de usuario cerca del usuario, pero los servidores están todos juntos en una misma sala. Esa sala tiene carios nombres: CPD (Centro de Proceso de Datos), centro de cálculo, datacenter, sala fría, pecera, etc. Centralizando se consigue:

*   **Ahorrar en costes de protección y mantenimiento**. No necesitan duplicar la vigilancia, la refrigeración, etc.
*   **Optimizar las comunicaciones entre servidores**. Al estar unos cerca de otros no necesitan utilizar cables largos o demasiados elementos intermedios que reducen el rendimiento.
*   **Aprovechar mejor los recursos humanos del departamento de informática**. No tienen que desplazarse a distintos edificios para realizar instalaciones, sustituir tarjetas, etc.

Todas las empresas deben tener documentado un plan de recuperación ante desastres (PLAN DE CONTINGENCIAS), donde se describa con el máximo detalle (en una crisis no hay tiempo para reflexionar) qué hacer ante una caída de cualquiera de los servidores que presta el CPD. El plan debe incluir:

*   **Hardware**. Qué modelos de máquinas tenemos instalados (tanto servidores como equipamiento de red), qué modelos alternativos podemos utilizar y cómo se instalarán.
*   **Software**. Qué sistema operativo y aplicaciones están instalados, con el número de versión actualizado y todas las opciones de configuración.
*   **Datos**. Qué sistema de almacenamiento utilizamos, con qué configuración y cómo se hace el respaldo de datos.

Tipos de servidores[](#tipos-de-servidores)
-------------------------------------------

![Servidor tipo rack](https://marcosruiz.github.io/assets/img/que-es-un-cpd/rack.jpg) _Servidor tipo rack_

![Servidor tipo blade](https://marcosruiz.github.io/assets/img/que-es-un-cpd/blade.jpg) _Servidor tipo blade_


| **Característica**       | **Servidores tipo rack**        | **Servidores tipo blade**        |
|--------------------------|----------------------------------|-----------------------------------|
| **Diseño**               | Cada servidor es independiente. | Los blades comparten un chasis.  |
| **Densidad**             | Menor.                          | Mayor.                           |
| **Refrigeración**        | Cada servidor tiene su propio sistema. | Compartida en el chasis.         |
| **Coste inicial**        | Más económico.                  | Más elevado.                     |
| **Gestión**              | Individual por servidor.        | Centralizada en el chasis.       |
| **Usos recomendados**    | Infraestructuras pequeñas o medianas. | Centros de datos grandes.        |

Protección[](#protección)
-------------------------

La información es vital para la empresa: si los servidores se paran, la empresa se para. Sucede en todos los sectores: en una empresa de telefonía, en una compañía aérea, en unos grandes almacenes…

El CPD debe estar protegido al máximo:

*   Elegimos un edificio en una zona con baja probabilidad de accidentes naturales.
*   También evitaremos la proximidad de ríos, playas, presas, aeropuertos, autopistas, bases militares, centrales nucleares, etc.
*   Evitaremos ubicaciones donde los edificios vecinos al nuestro pertenezcan a empresas dedicadas a actividades potencialmente peligrosas.
*   Preferentemente seleccionaremos las primeras plantas del edificio:
    *   La plata baja está expuesta a sabotajes desde el exterior.
    *   Las plantas subterráneas serian las primeras afectadas por una inundación.
    *   Las plantas superiores están expuestas a un accidente aéreo y, en caso de incendio iniciado en plantas inferiores, es seguro que nos afectara.
*   Se recomienda que el edificio tenga dos accesos y por calles diferentes. Así siempre podremos entrar en caso de que una estrada quede inaccesible.
*   Es recomendable evitar señalizar la ubicación del CPD para dificultar su localización a posibles atacantes.
*   Los pasillos que llevan hasta el CPD deben ser anchos por que algunos equipos son bastantes voluminosos. Incluso conviene dotarlo de un muelle de carga y descarga.
*   El acceso a la sala debe estar muy controlado. Los servidores solo interesan la personal del CPD.
*   En las paredes de la sala se deberá utilizar pintura plástica por que facilita su limpieza y se evita la generación de polvo.
*   En la sala se utilizará falso suelo y falso techo porque facilita la distribución del cableado y ventilación.
*   La altura de la sala será elevada tanto para permitir el despliegue del falso suelo y falso techo como para acumular muchos equipos en vertical.
*   En empresas de alta seguridad, la sala del CPD se recubre con un cofre de hormigón para protegerla de instrucciones desde el exterior.
*   Instalaremos equipos de detección de humos y sistemas automáticos de extinción de incendios.
*   El mobiliario de la sala debe utilizar materiales ignífugos.

Aislamiento[](#aislamiento)
---------------------------

Las máquinas que situamos en el CPD utilizan circuitos electrónicos. Por tanto, hay que protegerlas ante:

*   **Temperatura**: Los circuitos de los equipos, en especial los procesadores, trabajan a alta velocidad, por lo que generan muchos calor. Si además le sumamos la temperatura del aire, los equipos pueden tener problemas.
*   **Humedad**: No solo el agua, también un alto porcentaje de humedad en el ambiente puede dañarnos. Para evitarlo utilizaremos deshumidificadores.
*   **Interferencias electromagnéticas**. El CPD debe estar alejado de equipos que generan estas interferencias, como material industrial o generadores de electricidad, sean nuestros o de alguna empresa vecina.
*   **Ruido**: Los ventiladores de las máquinas del CPD generan mucho ruido, tanto que conviene introducir aislamiento acústico para no afectar a los trabajadores de las salas adyacentes.


Ventilación[](#ventilación)
---------------------------

Los CPD no cuelen tener ventanas. Las ventilación que conseguiríamos con ellas sería mínima para todo el calor que se genera, y el riesgo de intrusiones desde el exterior no es admisible en una instalación de tanta importancia.

La temperatura recomendada en la sala estría entre 21 y 23ºC. Para conseguirlo instalaremos equipos de climatización.

En los CPD grandes se adopta la configuración de pasillos calientes y pasillos fríos.

![Pasillos frios y calientes](https://www.researchgate.net/profile/Harold-Vacca-Vision-Electronica/publication/337994370/figure/fig5/AS:874832761737216@1585587792147/Figura-9-Disposicion-general-de-un-centro-de-datos-Sistema-pasillo-frio-caliente-38.jpg)

Un buen cable-management facilita la ventilación de los componentes electrónicos del CPD.

![Mal cable management](https://marcosruiz.github.io/assets/img/que-es-un-cpd/malCableManagement.webp) _Mal cable management_

![Buen cable management](https://marcosruiz.github.io/assets/img/que-es-un-cpd/buenCableManagement.webp) _Buen cable management_

Puedes leer el artículo [El #cableporn te convencerá de que los cables pueden llegar a ser increíblemente bonitos](https://www.xataka.com/componentes/cableporn-te-convencera-que-cables-pueden-llegar-a-ser-increiblemente-bonitos-1) en el que se ve cable-management nivel dios.

Suministros eléctrico y comunicaciones[](#suministros-eléctrico-y-comunicaciones)
---------------------------------------------------------------------------------

Nuestro CPD no está aislado: necesita ciertos servicios del exterior. Los principales son la alimentación eléctrica y las comunicaciones. En ambos casos conviene controlar con dos empresas distintas, de manera que un fallo en una compañía suministradora no nos impida seguir trabajando.

Control de acceso[](#control-de-acceso)
---------------------------------------

Las máquinas del CPD son vitales para la empresa y solo necesitan ser utilizados por un reducido grupo de especialistas. El acceso a esta sala de máquinas debe estar especialmente controlado.

En instalaciones importantes, el CPD puede tener su propio equipo de vigilantes de seguridad. En la sala se suele instalar también una red de sensores de presencia y cámaras de vídeos para detectar visitas inesperadas.

Monitorización[](#monitorización)
---------------------------------

El sistema de monitorización permite controlar parámetros críticos y fundamentales de un CPD. Permite conocer el estado de los equipos, planificar su ubicación y restitución, controlar valores relacionados con la temperatura, humedad y estado de los sensores, así como el estado de los sistemas de alimentación ininterrumpida, y programar tareas de mantenimiento.

[Comprobar la temperatura de CPU en Linux](https://protegermipc.net/2021/02/08/comprobar-la-temperatura-de-cpu-en-ubuntu-linux/)

[Psensor, el interfaz gráfica para lm-sensors](https://ubunlog.com/psensor-interfaz-lm-sensors/#Configura_lm-sensors)

CPDs en la nube[](#cpds-en-la-nube)
-----------------------------------

La base de la tecnología de centros de datos en la nube se basa en la contratación de no solo los servicios requeridos, sino también de la infraestructura tecnológica necesaria para proveer dichos servicios.

Ejemplos de CPDs en la nube:
*   Microsoft SCCM
*   Soluciones Azure
*   Amazon Web Services
*   Google Cloud Platform

Centro de respaldo
-------------------
A pesar de tanta protección, debemos pensar en la posibilidad de que ocurra una catástrofe en nuestro CPD y quede inservible (inundación, terremoto, sabotaje). La continuidad de la empresa no puede depender de un punto único de fallo; si disponemos de presupuesto suficiente, debemos instalar un segundo CPD.

Este segundo CPD, también llamado centro de respaldo (CR), ofrece los mismo servicios del centro principal (CP). Por supuesto, debe estar físicamente alejado del CP;cuantos más kilómetro entre ambos, mejor.

En condiciones normales, el CR está parado (stand-by) esperando que, en cualquier momento, la empresa pueda necesitar detener el CP y activar el CR como nuevo CP. Los usuarios no deben notar cambios. Para ellos la información del CP también está en el CR.

Como hemos señalado con anterioridad en el plan de recuperación ante desastres, puede que las circunstancias que nos lleven a conmutar el CR al CP sean muy urgentes y no haya tiempo para descubrir cómo se hace: todo el procedimiento de conmutación debe estar documentado con el máximo detalle, así como la posterior recuperación del CP. Incluso conviene probarlo una vez al año para confirmar que los pasos están bien descritos y el personal está capacitado para ejecutar bien.

Los equipos del centro principal y el centro de respaldo constituyen los centros de producción de la empresa: están en funcionamiento para dar servicio a los empleados, clientes y proveedores de la misma. Pero no son las únicas salas con servidores y equipamiento de res. Primero se prueba en un entorno controlado, llamado maqueta de preproducción, donde el personal de la empresa aplica el cambio.

Bibliografía[](#bibliografía)
-----------------------------

*   [SEGURIDAD PASIVA: EQUIPOS](http://aleogao.blogspot.com/2016/11/seguridad-pasiva-equipos.html)
*   [CPD: qué es un centro de procesamiento de datos y cómo funciona](https://www.xataka.com/pro/cpd-que-centro-procesamiento-datos-como-funciona)
*   [Top of Rack y End of Row: ¿Qué diferencia hay?](https://community.fs.com/es/blog/tor-vs-eor-data-center-architecture-design.html)