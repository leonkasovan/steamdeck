# steamdeck
Steamdeck Knowledge

Build EmulationStation Desktop Edition  
```
git clone https://gitlab.com/es-de/emulationstation-de.git
cd emulationstation-de/
sudo pacman -S curl freeimage freetype2 libgit2 pugixml poppler ffmpeg
cmake -DAPPIMAGE_BUILD=on -DSTEAM_DECK=on .
make -j8
```

# Emulator for Steamdeck
Nintendo Switch : (Suyu)  
```
wget https://git.suyu.dev/suyu/suyu/releases/download/v0.0.3/suyu--20240410-0de49070e4.AppImage -O /home/deck/Applications/yuzu.AppImage
```

Nintendo 3DS : (Lime3DS)  
```
wget https://github.com/Lime3DS/Lime3DS/releases/download/2111/lime3ds-2111-linux-appimage.tar.gz
tar -xvzf lime3ds-2111-linux-appimage.tar.gz
mv lime3ds-2111-linux-appimage/lime-qt.AppImage /home/deck/Applications/citra-qt.AppImage
rm -r lime3ds-2111-linux-appimage
```
