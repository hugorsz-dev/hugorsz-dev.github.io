# Pladur - Texto no seleccionable analizado con IA.
Este sistema te permite realizar consultas a través de IA al texto mostrado en la pantalla de una ventana específica. Está dirigido a videojuegos u otros tipos de programas donde el texto no es seleccionable. Para lograr este objetivo, utiliza el motor OCR de código abierto Tesseract y su biblioteca de Python, pythesseract.

## Instalación de Tesseract OCR
> [!Atención]
> Aunque las consultas se ejecutarán a través de una API, la conversión de imagen a texto mediante Tesseract se realizará localmente. Por lo tanto, si no tienes un ordenador con suficiente potencia, podrías experimentar ralentizaciones.

- Para ello, necesitas tener el programa instalado en una ubicación conocida, que debe estar indicada en el archivo config.json. [Descárgalo aquí](https://github.com/UB-Mannheim/tesseract/wiki).
- Y dentro de esa carpeta, en "tessdata" debe estar el archivo "spa.traineddata" (o el idioma de tu preferencia).  [Descárgalo aquí](https://github.com/tesseract-ocr/tessdata).

## Configuración
- El archivo `config.json` establecerá la ruta a la que se accederá para ejecutar Tesseract, la consulta realizada por la IA y el nombre de la ventana. Es esencial que esté correctamente rellenado para evitar errores durante la ejecución.
- El archivo `headers.json` contiene información relativa a la API a través de la cual se redirigirá el flujo de información. El formato está en formato RAPID API. ¡Se puede utilizar cualquier sistema con un formato compatible, o puedes modificar el código según sea necesario!

## Ejecución
Con el programa abierto, ejecuta main.py. Cada vez que la ventana pierda el foco, el terminal de comandos devolverá la salida de la IA.

## Diagrama
El funcionamiento del programa se puede resumir en el siguiente diagrama.
![diagrama](https://github.com/hugoruizsanchez/pladur/assets/120595249/6bf4717c-1140-4dd5-9226-573d65e974bd)

## Licencia
Este proyecto está licenciado bajo la [Licencia MIT](https://opensource.org/licenses/MIT) - consulta el archivo [LICENSE](LICENSE) para más detalles.

### Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/pladur).