# steamdeck
Steamdeck Knowledge

Setting Dev Environment
```
sudo steamos-readonly disable
sudo sed -i '/^SigLevel/ s/.*/SigLevel = Never/' /etc/pacman.conf
sudo pacman -Sy gcc cmake make autoconf binutils pkg-config
sudo pacman -Sy gcc glibc linux-api-headers alsa-lib libx11 xorgproto gtk3 glib2 libxcursor libxrandr pango libxrender libxinerama harfbuzz libxi cairo gdk-pixbuf2 libxext libxfixes at-spi2-core libglvnd sdl2
wget https://go.dev/dl/go1.22.2.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.22.2.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
sed -i '$a\export PATH=$PATH:/usr/local/go/bin' ~/.bashrc
sudo steamos-readonly enable
```

Build EmulationStation Desktop Edition  
```
git clone https://gitlab.com/es-de/emulationstation-de.git
cd emulationstation-de/
sudo pacman -S curl freeimage freetype2 libgit2 pugixml poppler ffmpeg
cmake -DAPPIMAGE_BUILD=on -DSTEAM_DECK=on .
make -j8
```

Update EmulationStation Desktop Edition in ES-DE.AppImage
```
cd ~/Applications
./ES-DE.AppImage --appimage-extract
wget https://github.com/AppImage/appimagetool/releases/download/continuous/appimagetool-x86_64.AppImage
chmod 0755 appimagetool-x86_64.AppImage
cp /path/to/es-de ~/Applications/squashfs-root/usr/bin
./appimagetool-x86_64.AppImage squashfs-root
mv ES-DE-x86_64.AppImage ES-DE.AppImage 
```

This option removes all non-Steam entries, regardless of how they were added to Steam.  
```
In Desktop Mode, exit out of Steam
Navigate to ~/.steam/steam/userdata/YOURSTEAMUSERID/
Delete the config folder
Delete the 760 folder
Reopen Steam and validate that your ROMs were properly removed
```

# ROMS source
https://r-roms.github.io/  

# Emulator for Steamdeck
A Symbian OS/N-Gage emulator
```
https://github.com/EKA2L1/EKA2L1
```

Nintendo Switch : (Suyu)  
```
wget https://git.suyu.dev/suyu/suyu/releases/download/v0.0.3/suyu--20240410-0de49070e4.AppImage -O /home/deck/Applications/yuzu.AppImage
wget https://github.com/THZoria/NX_Firmware/releases/download/18.0.1/Firmware.18.0.1.zip -P /home/deck/Emulation/bios/yuzu/firmware/
unzip /home/deck/Emulation/bios/yuzu/firmware/Firmware.18.0.1.zip -d /home/deck/Emulation/bios/yuzu/firmware/
rm /home/deck/Emulation/bios/yuzu/firmware/*.zip
wget https://github.com/leonkasovan/steamdeck/releases/download/v.1.0/nsk.zip -P /home/deck/Emulation/bios/yuzu/keys/
unzip /home/deck/Emulation/bios/yuzu/keys/nsk.zip -d /home/deck/Emulation/bios/yuzu/keys/
rm /home/deck/Emulation/bios/yuzu/keys/*.zip
```

Nintendo 3DS : (Lime3DS)  
```
wget https://github.com/Lime3DS/Lime3DS/releases/download/2111/lime3ds-2111-linux-appimage.tar.gz
tar -xvzf lime3ds-2111-linux-appimage.tar.gz
mv lime3ds-2111-linux-appimage/lime-qt.AppImage /home/deck/Applications/citra-qt.AppImage
rm -r lime3ds-2111-linux-appimage
```
