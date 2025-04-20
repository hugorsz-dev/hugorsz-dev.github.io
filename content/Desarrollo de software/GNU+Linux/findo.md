Una utilidad de línea de comandos escrita en Rust que busca archivos que contienen texto específico y organiza los resultados por estructura de directorios en varios formatos de salida.

## Descripción general

Findo utiliza el comando `grep` de Linux para buscar recursivamente archivos que contienen una cadena específica. Luego organiza los resultados en un mapeo de directorio a archivos y devuelve los datos en el formato que prefieras (JSON, YAML o CSV).

## Características

- Búsqueda rápida y recursiva de contenido de archivos usando `grep -rl`
- Varios formatos de salida soportados:
  - JSON (`-json`)
  - YAML (`-yaml`)
  - CSV con diferentes diseños:
    - Diseño vertical (`-csv` o `-csv-vertical`)
    - Diseño horizontal (`-csv-horizontal`)
- Agrupa automáticamente los archivos por directorio

## Requisitos

- Sistema operativo Linux (utiliza el comando `grep`)
- Rust y Cargo instalados

## Instalación

Clona el repositorio y construye el proyecto:

```bash
git clone [url-del-repositorio]
cd findo
cargo build --release
```

El ejecutable estará disponible en `target/release/findo`.

## Uso

```bash
findo <texto_a_buscar> <ruta_de_búsqueda> <formato_de_salida>
```

### Argumentos

- `<texto_a_buscar>`: La cadena de texto a buscar en los archivos
- `<ruta_de_búsqueda>`: La ruta del directorio para buscar recursivamente
- `<formato_de_salida>`: Uno de los siguientes:
  - `-json`: Resultados en formato JSON
  - `-yaml`: Resultados en formato YAML
  - `-csv`: Resultados en formato CSV vertical (diseño CSV predeterminado)
  - `-csv-vertical`: Igual que `-csv`
  - `-csv-horizontal`: Resultados en formato CSV horizontal

### Ejemplos

Buscar archivos que contengan "/domain" en el directorio `/hugo/Escritorio/archivos` y mostrar en formato JSON:

```bash
findo "/domain" /hugo/Escritorio/archivos -json
```

La misma búsqueda con salida YAML:

```bash
findo "/domain" /hugo/Escritorio/archivos -yaml
```

La misma búsqueda con salida CSV:

```bash
findo "/domain" /hugo/Escritorio/archivos -csv
```

## Formatos de salida

### JSON

Los resultados se organizan como un objeto JSON donde las claves son rutas de directorio y los valores son matrices de nombres de archivo:

```json
{
  "/ruta/al/directorio1": ["archivo1.txt", "archivo2.txt"],
  "/ruta/al/directorio2": ["archivo3.txt", "archivo4.txt"]
}
```

### YAML

Organización similar a JSON pero en formato YAML:

```yaml
/ruta/al/directorio1:
  - archivo1.txt
  - archivo2.txt
/ruta/al/directorio2:
  - archivo3.txt
  - archivo4.txt
```

### CSV Vertical

La primera fila contiene rutas de directorio, y las filas siguientes contienen archivos de cada directorio:

```
/ruta/al/directorio1, /ruta/al/directorio2
archivo1.txt, archivo3.txt
archivo2.txt, archivo4.txt
```

### CSV Horizontal

Cada línea comienza con una ruta de directorio seguida de los archivos en ese directorio:

```
/ruta/al/directorio1, archivo1.txt, archivo2.txt
/ruta/al/directorio2, archivo3.txt, archivo4.txt
```

## Limitaciones

- Funciona solo en sistemas Linux debido a la dependencia del comando `grep`
- Los conjuntos de resultados grandes pueden consumir una cantidad significativa de memoria, ya que todos los resultados se almacenan en memoria antes de procesarse

## Dependencias

- `std::collections::HashMap` - Para almacenar el mapeo de directorio a archivos
- `serde_json` - Para serialización JSON
- `serde_yaml` - Para serialización YAML
- `std::process::Command` - Para ejecutar el comando `grep`

## Acceso al repositorio

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/findo).