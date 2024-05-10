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
