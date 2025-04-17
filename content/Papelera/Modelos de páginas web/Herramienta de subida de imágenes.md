## Interfaz web que permite la subida de archivos mediante *drag and drop* via PHP 
![alt text](subida-archivos-archivo-cargado.png)

Tras la caída de [Anonfiles](https://old.reddit.com/r/privacy/comments/15oiqwr/did_anon_files_shut_down/?tl=es-es), un servicio privado de subida de archivos, decidí alojar mi propia alternativa de uso exclusivamente personal dentro de un <abbr title="Servidor virtual privado">VPS</abbr>. 

El exilio de este proyecto en la papelera responde a su evidente simplicidad. Treinta líneas de código en PHP, y su imprescun paupérrimo estilo 


## Funcionamiento

El enlace proporcionado debajo del panel de subida es un enlace directo al archivo, que del lado sel servidor será guardado en el directorio `uploads`. De instalarse, resultará indispensable proteger el acceso a la página - al menos en mi caso particular, empleé un sencillo fichero de restricción `.htpaccess` -.

## Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/trash/tree/main/upload-files/subir-archivos).
