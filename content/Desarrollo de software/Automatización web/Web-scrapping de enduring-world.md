![](enduring-world.png)

# Scraper de Comentarios

Una utilidad en Python para descargar y compilar los comentarios de la web de [Enduring Word (versión en español)](https://es.enduringword.com/).

## Descripción General

Este script descarga sistemáticamente comentarios bíblicos desde la versión en español del sitio web de Enduring Word (`es.enduringword.com`), organizándolos por libro y capítulo para un fácil acceso. Luego compila todo el contenido descargado en un único archivo HTML completo.

## Características

- **Cobertura Bíblica Completa**: Descarga comentarios para los 66 libros de la Biblia
- **Descarga Inteligente**: Detecta patrones de numeración de páginas y se adapta según corresponda
- **Capacidad de Reanudación**: Puede continuar descargas interrumpidas
- **Verificación de Integridad**: Comprueba capítulos y libros faltantes
- **Salida Consolidada**: Combina todos los comentarios en un único documento HTML que se puede buscar

## Requisitos

- Python 3.x
- Paquetes requeridos (instalar vía pip):
  ```
  pip install requests beautifulsoup4
  ```

## Uso

1. Clona este repositorio:
   ``` bash
   git clone https://github.com/tunombredeusuario/scraper-comentarios-biblicos.git
   cd scraper-comentarios-biblicos
   ```

2. Ejecuta el script:
   ``` bash
   python scraper.py
   ```

3. El script:
   - Creará un directorio llamado `html` para almacenar archivos individuales
   - Descargará comentarios para cada libro y capítulo
   - Mostrará el progreso en la consola
   - Compilará todo en `output.html` al completar

Si has ejecutado previamente el script y deseas reanudar una descarga:
- Responde `Y` cuando se te pregunte si deseas continuar la descarga existente
- Responde `N` para comenzar de nuevo

## Cómo Funciona

1. **Inicialización**: Configura nombres de libros y recuentos de capítulos
2. **Detección de Patrones de URL**: Determina si el sitio web utiliza ceros a la izquierda en los números de capítulo
3. **Proceso de Descarga**: Descarga sistemáticamente el comentario de cada capítulo
4. **Manejo de Excepciones**: Contiene casos especiales para URLs no estándar
5. **Compilación**: Fusiona todos los archivos HTML en un único documento

## Estructura de Directorios

```
scraper-comentarios-biblicos/
├── scraper.py          # Script principal
├── html/               # Directorio para archivos descargados
│   ├── genesis/        # Directorios de libros individuales
│   │   ├── 1.html
│   │   ├── 2.html
│   │   └── ...
│   ├── exodo/
│   └── ...
└── output.html         # Documento final compilado
```

## Notas

- Este script está diseñado específicamente para la versión en español de Enduring Word
- El script incluye manejo para casos especiales donde se combinan múltiples capítulos
- Sea respetuoso con los recursos del sitio web no ejecutando el script innecesariamente

###  Acceso al repositorio 

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/enduring-world-download).