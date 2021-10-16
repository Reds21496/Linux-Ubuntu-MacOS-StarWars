# Linux-Ubuntu-MacOS-StarWars
MacOS - Star Wars Theme for Ubuntu 20.04

Source Files:
- https://www.pling.com/p/1403328/
- https://www.pling.com/p/1355701
- https://www.gnome-look.org/p/1405756/
- https://albertlauncher.github.io/installing/


1. Instalar Google Chrome.
2. Ejecutar el siguiente script (asignar permisos de ejecucion)
 
```
#!/bin/bash

#-------Clonar repo y mover archivos
sudo apt install git gnome-shell-extensions chrome-gnome-shell gnome-tweak-tool -y
sudo git clone https://github.com/Reds21496/Linux-Ubuntu-MacOS-StarWars.git ~/StarWarsTheme
sudo cp -r ~/StarWarsTheme/themes/* /usr/share/themes/
sudo cp -r ~/StarWarsTheme/icons/* /usr/share/icons
sudo cp -r ~/StarWarsTheme/walls/* /usr/share/backgrounds/

#-------Albert
sudo curl https://build.opensuse.org/projects/home:manuelschneid3r/public_key | sudo apt-key add -
sudo echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_20.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo wget -nv https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_20.04/Release.key -O "/etc/apt/trusted.gpg.d/home:manuelschneid3r.asc"
sudo apt update
sudo apt install albert -y

#-------Plank
sudo add-apt-repository ppa:ricotz/docky
sudo apt-get update
sudo apt-get install plank -y

#-------Mover Tema de Plank
sudo mv ~/StarWarsTheme/themes/WhiteSur-dark/plankBigSurDark /usr/share/plank/themes
sudo mv ~/StarWarsTheme/themes/WhiteSur-light/plankBigSurLight /usr/share/plank/themes

#-------Eliminar Barra Lateral
sudo apt remove gnome-shell-extension-ubuntu-dock -y
```

3. Reiniciar el PC
4. Habilitar GNOME extensions en Google: https://chrome.google.com/webstore/detail/gnome-shell-integration/gphhapmejobijbbhgpjhcjognlahblep
5. Instalar User Themes: https://extensions.gnome.org/extension/19/user-themes/
6. Seleccionar Temas en tweaks (retoques) -> Appearance -> Applications -> WhiteSur-light
7. Seleccionar Cursor en tweaks (retoques) -> Appearance -> Cursor -> McMojave-cursors
8. Seleccionar Icons en tweaks (retoques) -> Appearance -> Icons -> WhiteSur
9. Seleccionar Shell en tweaks (retoques) -> Appearance -> Shell -> WhiteSur-dark
10. Configurar Plank a gusto (Seleccionar tema, opacidad y tamano):
```
plank --preferences
```
9. Abrir Albert y establecer hotkey, theme (spotlight), elegir extensiones y autostart login
10. Instalar Arc Menu: https://extensions.gnome.org/extension/3628/arcmenu/
11. Click Derecho en el logo del Arc Menu y Button Appearance. Seleccionar Icono: /usr/share/icons/ArcMenuLogo/ImperialLogoWhite.png
12. Instalar Efecto Magic Lamp: https://extensions.gnome.org/extension/3740/compiz-alike-magic-lamp-effect/
13. Reiniciar por ultima vez para que se ejecuten todos los cambios
