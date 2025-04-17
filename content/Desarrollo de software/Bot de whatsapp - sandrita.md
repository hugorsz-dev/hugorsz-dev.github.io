## Sandrita es un bot de Whatsapp programado en Python, destacable por su fácil extensibilidad.

![](wppserver.png)

Todas las operaciones realizadas por Sandrita utilizan el módulo `wpp_requests` - ver el repositorio actual - un conjunto de funciones diseñadas para realizar peticiones a la [API del Servidor WPP Connect](https://github.com/wppconnect-team/wppconnect-server). Para utilizar esta herramienta, es esencial instalar y configurar este servicio o desarrollar un módulo personalizado para reemplazar el sistema de peticiones predeterminado.

### Funcionamiento

El funcionamiento de Sandrita consiste en un bucle infinito interrumpido por un número variable de segundos entre cada ciclo. Para cada uno de estos ciclos, como mínimo, se realiza una petición `get` a la API utilizando el módulo *request*, para recibir un conjunto de mensajes que luego son manipulados por las funciones designadas para ejecutarse.

1. Inicio del bucle: petición `get` que almacena los mensajes recibidos en memoria.
2. Manipulación de los mensajes recibidos según las funciones definidas en el bucle.
3. Fin del bucle, tiempo de espera hasta que se repite.

### Módulos

### data

El módulo `data` controla la entrada y salida de datos. La entrada generalmente se almacena en un archivo de configuración llamado `config.json`, y la salida de cada módulo se almacena en su respectivo archivo, `variables.json`.

Las funciones `get` y `set` pueden ejecutarse en cualquier parte del código donde este módulo esté importado.

El propósito de este sistema, además de la intercomunicación entre módulos, es ser completamente configurable desde el chat de Whatsapp, un objetivo parcialmente logrado en algunos casos pero incompleto, debido a los siguientes problemas pendientes referenciados en la sección *TODO* de `main.py`:

- Todas las variables deberían ser reemplazadas (aquellas en el encabezado) para llamar directamente al módulo `data`.
- Por lo tanto, las variables de `config.json` deberían reasignarse a nivel de función.

#### Deficiencias Pendientes por Resolver

- Las variables relacionadas con las ubicaciones de archivos no se refieren al `path` en `config.json`, lo cual no es un problema siempre que los archivos no cambien de ubicación.

### wpp_requests

Utilizando el módulo nativo `requests`, los métodos de *WPP Connect* se adaptan para que puedan ser utilizados por los diferentes módulos de Sandrita. La extensión de este módulo depende de la necesidad, y este proyecto no pretende extenderlo a toda la amplitud de las funciones ofrecidas por la API, siempre que no sean utilizadas.

### boot

La caché suele ser un problema. *WPP Connect* utiliza una instancia de Chromium para operar, que tiende a acumular memoria que normalmente se libera después de cada reinicio. Así, `wpp_boot` mantiene un contador que, después de alcanzar un número específico de ciclos en `config.json`, ejecuta el archivo `execute_previusly.sh`, con instrucciones para detener e iniciar servicios.

Antes de inicializar el sistema, comprueba que efectivamente está conectado.

No es aconsejable activar esta función si hay suficiente memoria RAM.

### info

Su objetivo principal es recopilar mensajes llamando a la petición `get_messages()`. Para ahorrar recursos, esta petición se ejecuta solo una vez durante un intervalo específico de mensajes, establecido en `config.json`, y se almacena dentro de las variables específicas establecidas para este módulo, `variables.json`.

Además, `info` recopila estadísticas, como el número total de mensajes o el número total de reinicios.

### spam_detector

El detector de spam está diseñado para recibir un conjunto de mensajes cada pocos segundos especificados en `config.json`, y analizar si el resultado se ajusta al algoritmo de detección, que **actualmente solo detecta spam de Whatsapp y no otras fuentes** y no tiene **prevención de flood**. Esto podría ser una buena idea para futuros módulos.

#### Significado de las Variables

- `default_big_spam_alert`: Duración del modo de prevención intensiva de spam (esencialmente, cuánto dura el bloqueo de mensajes).
- `default_timer_big_spam_alert`: Duración del tiempo que el modo de prevención intensiva de spam (big_spam) dura, durante el cual el grupo estará restringido para enviar mensajes.
- `default_timer_reboot`: Ciclos en los que el servicio tarda en reiniciarse (tiempo de recarga, depende de cuánto hable el grupo).
- `default_spam_message_limit_for_alarm`: Mensajes de spam en los que el sistema activa la alerta.
- `default_normal_time_sleep`: Duración del ciclo mientras todo está normal.
- `default_big_spam_alert_time_sleep`: Duración del ciclo mientras está en modo big_spam.
- `default_while_normal_deleting_time_sleep`: Duración del ciclo de eliminación mientras todo está normal.
- `default_while_big_spam_deleting_time_sleep`: Duración del ciclo de eliminación mientras está en modo big_spam.

### reminders

Sistema de recordatorios, que envía un mensaje con un recordatorio aleatorio cada cierto intervalo de mensajes especificado en `config.json`.

### msg_requests

Intérprete y gestor de comandos introducidos por el usuario en el chat. Dentro de este, se almacenan todos los módulos que requieren interacción directa con los usuarios; los usuarios que pueden acceder a las solicitudes deben estar registrados en el archivo `admins.json`.

El archivo `config.json` permite editar caracteres especiales con los que se llaman las solicitudes, alias para comandos asociados a módulos, e incluso respuestas a estos.

#### control_panel

El panel de control gestiona los archivos de configuración a través de Whatsapp. Esto tiene como objetivo proporcionar una configuración completa de Sandrita desde los mensajes (o al menos, este es el objetivo, ver la sección `data`).

Tiene las siguientes funciones:

- Ver el archivo de configuración (o módulo), formateado para Whatsapp.
- Filtrar archivo de configuración, seleccionando un path separado por comas para ver una parte específica del mismo.
- Modificar una parte específica de un archivo de configuración.
- Realizar un reinicio suave del sistema sin detener la ejecución del código.

##### Deficiencias Pendientes por Resolver

- Todos los problemas enumerados en la sección `data`.
- El archivo `admins.json` debería ser modificable, pero por ahora, los cambios deben hacerse manualmente.

#### state

Devuelve en formato Whatsapp información extraída del servidor, así como algunos datos recopilados del módulo info:

- Total de reinicios.
- Total de ciclos.
- Total de mensajes.
- Porcentaje de uso de RAM.
- Porcentaje de uso de CPU.
- Los servicios del servidor más exigentes, seguidos de una etiqueta de color que indica su estado.

#### manage_reminders

Gestiona los recordatorios, permitiendo su inclusión y eliminación.

#### man

En cada módulo de `config.json`, hay una sección de manual donde se describe cada comando y funcionalidad para que los usuarios que lo utilizarán puedan consultarlo.

### Demostración en vídeo 

<iframe width="1366" height="768" src="https://www.youtube.com/embed/db-KADjds0U" title="Explicación y demostración de SANDRITA - Bot de whatsapp en python" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/sandrita).