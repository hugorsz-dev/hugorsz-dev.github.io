# XBGG: Interfaz Gráfica de Brillo Xrandr para GTK4
<div align="center" style="margin-bottom: 0;">  
  <img src="https://github.com/user-attachments/assets/373ab630-763b-4ddf-b479-5644cdc0b253" />
</div>

Una aplicación GUI simple y moderna para ajustar el brillo y gamma de la pantalla en sistemas Linux usando xrandr y el stack gráfico Xorg.

## Características
- **Interfaz intuitiva**: GUI limpia y fácil de usar construida con GTK4
- **Control completo**: Ajustar brillo y gamma de forma independiente
- **Soporte multi-monitor**: Gestionar múltiples pantallas conectadas
- **Rendimiento optimal**: Desarrollado en Rust para máxima eficiencia
- **Integración nativa**: Utiliza xrandr directamente sin dependencias adicionales

## Requisitos
- Sistema operativo Linux
- Xorg (X11) - no compatible con Wayland
- xrandr instalado en el sistema
- GTK4

### Dependencias del sistema
#### Ubuntu/Debian
```bash
sudo apt install xrandr libgtk-4-dev
```
#### Fedora/RHEL
```bash
sudo dnf install xrandr gtk4-devel
```
#### Arch Linux
```bash
sudo pacman -S xorg-xrandr gtk4
```

## Instalación
### Desde releases
1. Descarga el binario más reciente desde [Releases](https://github.com/user/xrandr-brightness-gtk4-gui/releases)
2. Hazlo ejecutable: `chmod +x xrandr-brightness-gtk4-gui`
3. Muévelo a tu PATH: `sudo mv xrandr-brightness-gtk4-gui /usr/local/bin/`

### Compilar desde el código fuente
#### Prerrequisitos
- Rust (versión 1.70 o superior)
- Cargo

#### Pasos
```bash
# Clonar el repositorio
git clone https://github.com/user/xrandr-brightness-gtk4-gui.git
cd xrandr-brightness-gtk4-gui

# Compilar
cargo build --release

# El binario estará en target/release/
```

## Resolución de problemas
### La aplicación no detecta las pantallas
```bash
# Verificar que xrandr funciona
xrandr --listmonitors

# Verificar que estás usando Xorg
echo $XDG_SESSION_TYPE
```

### Permisos insuficientes
```bash
# Asegúrate de que tu usuario puede ejecutar xrandr
xrandr --help
```

### Problemas de compilación
```bash
# Actualizar Rust
rustup update

# Limpiar y recompilar
cargo clean
cargo build --release
```

###  Acceso al repositorio 

Puedes ver y descargar el repositorio en [esta página de GitHub](https://github.com/hugorsz-dev/xrandr-brightness-gtk4-gui).