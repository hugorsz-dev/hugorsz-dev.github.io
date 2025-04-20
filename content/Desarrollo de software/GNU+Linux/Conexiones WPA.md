## Script para wireless-tools que facilita la conexión a redes wifi WPA desde la terminal

![Imagen GNU/Linux](wirelesstools.png)

Para equipos que no hacen uso de entornos de escritorio que faciliten la tarea de mantener una conexión wifi con cifrado WPA, desarrollé un script en bash que emplea las utilidades **wireless-tools** (`ifconfig`, `iwlist`, `iwconfig`, `dhclient`, `wpa_supplicant`).

El programa recibe dos parámetros de entrada: nombre de la red y contraseña, que posteriormente archiva en un fichero de configuración que utiliza - hasta ser modificado - para establecer la conexión cada vez que se llama.

###  Acceso al repositorio 

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/script-wpa-wifi).

