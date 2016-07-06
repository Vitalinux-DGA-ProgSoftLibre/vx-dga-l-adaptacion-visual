# Paquete DEB vx-dga-l-adaptacion-visual

Paquete encargado de personalizar el aspecto del entorno de Escritorio y Explorador de Archivos PCmanFM de Lubuntu/Vitalinux, con la finalidad de:

1. Aumentar los tamaños de los iconos del Escritorio y Explorador de Archivos:
  * Archivo: ~/.config/libfm/libfm.conf
  * Directiva: big_icon_size=96
2. Aumentar el tamaño de la letra: 
  * Archivo: ~/.config/pcmanfm/lubuntu/desktop-items-0.conf
  * Directiva: desktop_font=Ubuntu 16
3. Cambiar el tamaño del Ratón:
  * Archivo: ~/.config/lxsession/Lubuntu/desktop.conf
  * Directiva: iGtk/CursorThemeSize=72

# Usuarios Destinatarios

Muy útil para usuarios con dificultades visuales.

# Aspectos Interesantes:
La configuración de la adaptación visual se hace tanto al iniciar sesión, `/etc/xdg/autostart/adaptacion-visual.desktop`, como al cerrar sesión en el caso de que exista el script `/usr/bin/tareas-logout` y este configurado para ello el `/etc/lightdm/lightdm.conf` con la directiva `session-cleanup-script=/usr/bin/tareas-logout`

# Como Crear el paquete DEB a partir del codigo de GitHub
Para crear el paquete DEB será necesario encontrarse dentro del directorio donde localizan los directorios que componen el paquete.  Una vez allí, se ejecutará el siguiente comando (es necesario tener instalados los paquetes apt-get install debhelper devscripts):

```
apt-get install debhelper devscripts
/usr/bin/debuild --no-tgz-check -us -uc
```

# Como Instalar el paquete generado vx-dga-l-lupa*.deb:
Para la instalación de paquetes que estan en el equipo local puede hacerse uso de ***dpkg*** o de ***gdebi***, siendo este último el más aconsejado para que se instalen también las dependencias correspondientes.
```
dpkg -i vx-dga-adaptacion-visual*.deb
gdebi vx-dga-adaptacion-visual*.deb
```
