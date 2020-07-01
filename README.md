# Моя альтернативная установка шрифтов для WPS Office
Я добавила к текущим шрифтам, которых не у автора (откуда я сделала форк), дополнительные шрифты для WPS Office. Это особо актуально для Ubuntu.
Сам WPS Office качается из стандартных установщиков вашей операционки. Либо можно скачать отсюда https://linux.wps.com дистрибутив .deb для Ubuntu или .rpm для CentOS.

Ubuntu, Pop OS и подобные дистрибутивы.
```
sudo add-apt-repository multiverse
sudo apt install ttf-mscorefonts-installer
wget https://github.com/anutator/ttf-wps-fonts/raw/master/wps-fonts.tar.gz  # лучше скачать вручную
tar xvzf wps-fonts.tar.gz
cd wps-fonts
sudo ./install.sh
```
CentOS.

Отмечу, что для CentOS необязательно качать весь архив wps-fonts.tar.gz, потому что основные шрифты уже есть в первых двух пакетах. Нам нужен будет только шрифт mtextra.ttf.
```
sudo yum install msttcore-fonts-installer webcore-fonts
wget https://github.com/anutator/ttf-wps-fonts/raw/master/wps-fonts.tar.gz
tar xf wps-fonts.tar.gz
cd wps-fonts
sudo ./install.sh
```
Если необходимо отдельно обновить кэш шрифтов (вообще то уже в скрипт команда уже включена)
```
fc-cache -f -v
```

# WPS Office Fonts

These are the symbol fonts required by wps-office. They are used to display math formulas. We have collected the fonts here to make things easier.

## Arch Linux Installation

You can use the [ttf-wps-fonts](https://aur.archlinux.org/packages/ttf-wps-fonts/)  package from the AUR.

## Using the Install Script

You can use the install script on most distributions.

For this tutorial we will use the `/tmp` directory to temporary save the files.

Change to the `/tmp` directory.
```
cd /tmp
```

Clone the Git repository.
```
git clone https://github.com/iamdh4/ttf-wps-fonts.git
```

Enter the directory.
```
cd ttf-wps-fonts
```

Run the install script.
```
sudo bash install.sh
```

Clean up the `tmp` directory.
```
rm -rf /tmp/ttf-wps-fonts
```
## Manual Installation

For this tutorial we will use the `/tmp` directory to temporary save the files.

Change to the `/tmp` directory.
```
cd /tmp
```

Clone the Git repository.
```
git clone https://github.com/iamdh4/ttf-wps-fonts.git
```

Create a sub directory in your system's fonts directory. This is usually `/usr/share/fonts`, otherwise consult your distribution's documentation.
```
sudo mkdir /usr/share/fonts/wps-fonts
```

Move fonts to the new directory.
```
sudo mv ttf-wps-fonts/* /usr/share/fonts/wps-fonts
```

Fix the file permissions.
```
sudo chmod 644 /usr/share/fonts/wps-fonts/*
```
Rebuild the font cache.
```
sudo fc-cache -vfs
```

Clean up the `tmp` directory.
```
rm -rf /tmp/ttf-wps-fonts
```





