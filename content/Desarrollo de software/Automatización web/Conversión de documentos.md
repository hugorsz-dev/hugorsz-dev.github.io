##  Un portal que enlaza archivos PDF y HTML

Un discreto script programado en Python, que emplea las utilidades `soffice`, `pandoc` y `pdftohtml` para convertir mi biblioteca de documentos en una página web funcional. 

## Funcionamiento

> [!note] Antes de leer, considera que...
>Se trata de un **proyecto personal**, que se adecúa a las necesidades particulares de mi objetivo concreto, cuya estructura difiere a la de otro tipo de webs. No es un software de gestión automática de páginas webs, sino mi solución particular aplicada a un único contexto, publicado para ser utilizado como mera referencia y apoyo. 

1. Cada archivo está organizado en su correspondiente carpeta.

2. Un script escrito en bash, `exportar.sh`, crea una nueva estructura de carpetas y opera sobre los directorios de mi área de trabajo, convirtiendo automáticamente cada archivo en su interior en formatos *.pdf* y *.html*.

3. Este procedimiento usa las utilidades que brinda LibreOffice para la consola de comandos, denominadas `soffice`.

4. Las exportaciones en PDF siempre funcionan bien, pero cuando hago el mismo proceso con HTML, **el formato tiende a desajustarse**.

5. Finalmente, un programa escrito en Python, `compilar-web.py` inspecciona la estructura de carpetas creada por el script anterior, creando los archivos .html necesarios para enlazar todos los documentos en una página web completa y funcional.

###  Acceso al repositorio 

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/web-automatica-estudio-escrituras).