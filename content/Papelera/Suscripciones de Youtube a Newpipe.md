
![](https://linuxreviews.org/images/thumb/b/b7/Newpipe-01.jpg/1200px-Newpipe-01.jpg)

[Newpipe](https://newpipe.net/) es un frontend para Youtube **libre y de código abierto**. Permite visualizar y descargar vídeos de youtube; al tratarse de un servicio que acude a una API independiente, no permite el inicio de sesión con cuentas de google, y por extensión, debes ingresar suscripciones de nuevo. 

Con el objetivo de aminorar el tedioso trabajo de introducir decenas de suscripciones manualmente, diseñé un script que convertía el texto plano de las suscripciones de la página de Youtube en un formato JSON reconocido por la aplicación.

Ahora mismo el script está obsoleto, ya que Newpipe emplea otros formatos para realizar este trabajo. 

## Funcionamiento 

1. Importa JSON para trabajar con archivos en ese formato.
2. Lee las suscripciones desde un archivo de texto.
3. Crea un lugar para guardar la información de las suscripciones.
4. Busca nombres de canales y sus URLs en el texto.
5. Guarda los nombres y URLs en el formato correcto.
6. Escribe la información en un archivo JSON.

## Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/trash/blob/main/youtube_to_newpipe_json.py).

