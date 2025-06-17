# Base de datos del Libre Diccionario de la Lengua Española

Base de datos que contiene la casi totalidad de los vocablos de la lengua española, incluyendo las conjugaciones de todos sus verbos, junto con su definición, formas compuestas, sinónimos, entre otros recursos lexicográficos. 

## Generación automática. 
Para facilitar la labor del desarrollo, el script `generar.sh` gestionará automáticamente el proceso de creación de la base de datos a partir de los recursos. Para lo cual será preciso: 

- Tener instalado `python` y su gestor de dependencias, `pip`.

El contenido de la base de datos, sus redirecciones, apartados y vínculos pueden visualizarse mediante una herramienta realizada para facilitar el trabajo de resolución de errores y comprensión del sistema, `consultar_diccionario.py`, que accede al último fichero generado

## Recursos

- soloDefinicionesSinLema.md (modificado), extraído del Diccionario de la RAE, 2014 - en formato EBUP:
https://archive.org/details/realacademiaespanoladiccionariodelalenguaespanolaediciondeltricentenariorealacademiaespanola2014

- sinonimos.json, extraído del proyecto "sinonimos" basado en el proyecto OpenThesaurus 
https://github.com/edublancas/sinonimos/blob/master/sinonimos.json

- 0_palabras_todas_no_conjugaciones.txt
https://github.com/JorgeDuenasLerin/diccionario-espanol-txt

## Funcionamiento de cada uno de los scripts
![1](https://github.com/user-attachments/assets/5471aa6a-5023-4107-846f-da00190437b9)