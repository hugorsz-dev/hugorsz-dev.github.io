## Script para XRandR que posibilita la reducción del brillo de los monitores desde una interfaz de software

![Imagen GNU/Linux](terminal-ajustarbrillo.png)

El ecosistema de Windows facilita herramientas de control de brillo a las que me había habituado, pero de las que carecía en mis entornos con base Linux, por lo que esarrollé una utilidad dedicada a los entornos de escritorio que - todavía -  usan el protocolo X.ORG (la gran mayoría).

- Muestra en pantalla todos los monitores disponibles, en forma de lista numerada.
- Permite elegir un monitor determinado o todos los monitores a la vez.
- Ofrece la posibilidad de subir o bajar el brillo introduciendo porcentajes: 5% para el mínimobrillo, 100% para el máximo brillo, o +100% para dar mucha más claridad a la pantalla.
- Está limitado para evitar subir o bajar el brillo en rangos inconvenientes (>5% o <200%)

### Vídeo demostrativo

<iframe width="445" height="300" src="https://www.youtube.com/embed/ym_JQ0jMk6c" title="Ajustar brillo de la pantalla - Script en BASH - Linux" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

###  Acceso al repositorio 

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/script-brightness-adjustment-xrandr).