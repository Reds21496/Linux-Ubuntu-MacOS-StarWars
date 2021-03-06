# Linux-Ubuntu-MacOS-StarWars
MacOS - Star Wars Theme for Ubuntu 20.04

Source Files:
- https://www.pling.com/p/1403328/
- https://www.pling.com/p/1355701
- https://www.gnome-look.org/p/1405756/
- https://ulauncher.io/


1. Asignar permisos de ejecucion y ejecutar el siguiente script (puede ser requerido oprimir enter cuando el script se encuentra en ejecucion)
 
```
#!/bin/bash

#-------Actualizar repositorios e instalar los programas necesarios
sudo apt update
sudo apt upgrade -y
sudo apt install curl wget git gnome-shell-extensions chrome-gnome-shell gnome-tweak-tool -y

#-------Instalar Chrome
sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb

#-------Clonar repo y mover archivos
sudo git clone https://github.com/Reds21496/Linux-Ubuntu-MacOS-StarWars.git ~/StarWarsTheme
sudo cp -r ~/StarWarsTheme/themes/* /usr/share/themes/
sudo cp -r ~/StarWarsTheme/icons/* /usr/share/icons
sudo cp -r ~/StarWarsTheme/walls/* /usr/share/backgrounds/

#-------Instalar Ulauncher y tema White Sur
echo -ne '\n' | sudo add-apt-repository ppa:agornostal/ulauncher
sudo apt update
sudo apt install ulauncher
mkdir -p ~/.config/ulauncher/user-themes
git clone https://github.com/Raayib/WhiteSur-Light-ulauncher.git \
  ~/.config/ulauncher/user-themes/WhiteSur-Light-ulauncher

#-------Instalar Plank
echo -ne '\n' | sudo add-apt-repository ppa:ricotz/docky
sudo apt-get update
sudo apt-get install plank -y

#-------Mover Tema de Plank
sudo mv ~/StarWarsTheme/themes/WhiteSur-dark/plankBigSurDark /usr/share/plank/themes
sudo mv ~/StarWarsTheme/themes/WhiteSur-light/plankBigSurLight /usr/share/plank/themes

#-------Eliminar Barra Lateral
sudo apt remove gnome-shell-extension-ubuntu-dock -y
```

2. Reiniciar el PC
3. Habilitar GNOME extensions en Google Chrome: https://chrome.google.com/webstore/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep
4. Instalar User Themes: https://extensions.gnome.org/extension/19/user-themes/
5. Configurar Background, Theme, Icons, Cursors, etc...
```
gsettings set org.gnome.desktop.interface gtk-theme "WhiteSur-light"
gsettings set org.gnome.desktop.interface icon-theme 'WhiteSur'
gsettings set org.gnome.desktop.interface cursor-theme 'McMojave-cursors'
gsettings set org.gnome.desktop.background picture-uri 'file:///usr/share/backgrounds/darthvader.jpg'
gsettings set org.gnome.desktop.screensaver picture-uri 'file:///usr/share/backgrounds/darthvader.jpg'
```
6. Seleccionar Shell en tweaks (retoques) -> Appearance -> Shell -> WhiteSur-dark
7. Agregar Plank a las startup Applications en tweaks
8. Configurar Plank a gusto (Seleccionar tema, opacidad y tamano)
```
plank --preferences
```

9. Abrir Ulauncher y establecer autostart login
10. Instalar Arc Menu: https://extensions.gnome.org/extension/3628/arcmenu/
11. Click Derecho en el logo del Arc Menu y Button Appearance. Seleccionar Icono: /usr/share/icons/ArcMenuLogo/ImperialLogoWhite.png
12. (Opcional) Instalar Efecto Magic Lamp: https://extensions.gnome.org/extension/3740/compiz-alike-magic-lamp-effect/
13. (Opcional) Instalar Wobbly windows: https://extensions.gnome.org/extension/2950/compiz-alike-windows-effect/
14. (Opcional) Instalar Efecto Coverflow alt+tab: https://extensions.gnome.org/extension/97/coverflow-alt-tab/
15. (Opcional) Instalar net-speed: https://extensions.gnome.org/extension/4478/net-speed/
16. (Opcional) Instalar notificaciones transparentes: https://extensions.gnome.org/extension/1080/transparent-notification/
17. (Opcional) Modificar Login Screen Background: https://www.omgubuntu.co.uk/2022/01/change-ubuntu-login-screen-background
18. (Opcional) Modificar Scroll Speed (Probado en Ubuntu 20.04):
    - Install imwheel and adjust (to make things work):
      - Run sudo apt install imwheel
      - Run bash <(curl -s http://www.nicknorton.net/mousewheel.sh)
      - Using the slider adjust the scroll speed 'multiplier'. (I like it on 4/5)
    - Add imwheel as a startup application (to make things continue working after restart):
      - Open Apps -> Startup Applications
      - Add a new entry to the bottom of the list: Name= Wheel Scroll Speed, Command= imwheel, Comment= Activates wheel scroll speed fix on system startup (or whatever you like)
19. Reiniciar por ultima vez para que se ejecuten todos los cambios
