Para un proyecto en el que mi tarea consistía en recortar las descripciones más largas de ficheros `.yaml` escritos en la especificación de [Open API](https://swagger.io/specification/]). 

Como el propósito era tan particular, el script que me facilitaba el reporte de los archivos organizados por cantidad de palabras queda reducido a la papelera. 

# Funcionamiento

1. Iterará (walk) por todos los directorios que contengan un `.yaml`
2. Contemplará: 
    - Cada una de sus descripciones, tanto de resumen, de request, y su descripción introductoria
    - Cada enlace
3. Clasificará su contenido en base al número de palabras de su descripción, y la validez de los urls respectivamente. 
4. Exportará ficheros CSV para su visualización. 

## Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/trash/blob/main/detect_large_yaml.py).

