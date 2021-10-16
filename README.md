# Linux-Ubuntu-MacOS-StarWars
MacOS - Star Wars Theme for Ubuntu 20.04

Source Files:
- https://www.pling.com/p/1403328/
- https://www.pling.com/p/1355701
- https://www.gnome-look.org/p/1405756/
- https://albertlauncher.github.io/installing/


1. Ejecutar el siguiente script (asignar permisos de ejecucion)
 
```
#!/bin/bash

#-------Instalar Chrome
sudo apt update
sudo apt upgrade -y
sudo apt install wget
sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb

#-------Clonar repo y mover archivos
sudo apt install git gnome-shell-extensions chrome-gnome-shell gnome-tweak-tool -y
sudo git clone https://github.com/Reds21496/Linux-Ubuntu-MacOS-StarWars.git ~/StarWarsTheme
sudo cp -r ~/StarWarsTheme/themes/* /usr/share/themes/
sudo cp -r ~/StarWarsTheme/icons/* /usr/share/icons
sudo cp -r ~/StarWarsTheme/walls/* /usr/share/backgrounds/
sudo apt install curl -y

#-------Albert
sudo curl https://build.opensuse.org/projects/home:manuelschneid3r/public_key | sudo apt-key add -
sudo echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_20.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo wget -nv https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_20.04/Release.key -O "/etc/apt/trusted.gpg.d/home:manuelschneid3r.asc"
sudo apt update
sudo apt install albert -y

#-------Plank
sudo add-apt-repository ppa:ricotz/docky
echo
sudo apt-get update
sudo apt-get install plank -y

#-------Mover Tema de Plank
sudo mv ~/StarWarsTheme/themes/WhiteSur-dark/plankBigSurDark /usr/share/plank/themes
sudo mv ~/StarWarsTheme/themes/WhiteSur-light/plankBigSurLight /usr/share/plank/themes

#-------Eliminar Barra Lateral
sudo apt remove gnome-shell-extension-ubuntu-dock -y
```

2. Reiniciar el PC
3. Habilitar GNOME extensions en Google: https://chrome.google.com/webstore/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep
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

9. Abrir Albert y establecer hotkey, theme (spotlight), elegir extensiones y autostart login
10. Instalar Arc Menu: https://extensions.gnome.org/extension/3628/arcmenu/
11. Click Derecho en el logo del Arc Menu y Button Appearance. Seleccionar Icono: /usr/share/icons/ArcMenuLogo/ImperialLogoWhite.png
12. (Opcional) Instalar Efecto Magic Lamp: https://extensions.gnome.org/extension/3740/compiz-alike-magic-lamp-effect/
13. (Opcional) Instalar Wobbly windows: https://extensions.gnome.org/extension/2950/compiz-alike-windows-effect/
14. (Opcional) Instalar Efecto Coverflow alt+tab: https://extensions.gnome.org/extension/97/coverflow-alt-tab/
15. (Opcional) Instalar net-speed: https://extensions.gnome.org/extension/4478/net-speed/
16. (Opcional) Instalar notificaciones transparentes: https://extensions.gnome.org/extension/1080/transparent-notification/
17. Reiniciar por ultima vez para que se ejecuten todos los cambios
