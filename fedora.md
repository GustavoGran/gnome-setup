# gnome-setup
Repository for command line script to setup environment.
Why in flatpak? To get the most up to date apps.

## Fix Fedora Bluetooth
[Fedora Wiki: How to Debug Bluetooth Problems](https://fedoraproject.org/wiki/How_to_debug_Bluetooth_problems)

Instal bluez and tools
```
sudo dnf intstall bluez bluez-tools
```
Enable and start bluetooth daemon
```
sudo systemctl enable bluetooth.service
```
Start bluetooth
```
sudo systemctl start bluetooth.service
```

## Remove default apps that come with fedora and will not be used
- Rhythmbox
- Boxes
- LibreOffice
```
sudo dnf remove -y rhythmbox gnome-boxes
sudo dnf remove -y libreoffice*
sudo dnf autoremove -y
sudo dnf remove -y  --duplicates
```
## Install core system repo apps
Make sure your current apps and dependencies are updated
```
sudo dnf upgrade --refresh -y
```
- Gnome Sound Recorder to record sounds
- Video Downloader to get that youtube videos
- GIMP for image manipulation
```
sudo dnf install gnome-sound-recorder video-downloader gimp
```

## Install NVIDIA graphics drivers

Enable free RPM Fusion repository (third party)
```
sudo dnf install \
  https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
```

Enable non free RPM Fusion repository (third party)
```
sudo dnf install \
  https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
Refresh the repository list
```
sudo dnf update --refresh
```

Install latest NVIDIA drivers
```
sudo dnf install akmod-nvidia -y
```

Install cuda drivers
```
sudo dnf install xorg-x11-drv-nvidia-cuda
```

Reboot the computer
```
reboot
```

## Install and configure flatpak utilitary
Install flatpak utilitary if the distribution doesn't bring flatpaks by default
```
# If on Debian-based distributions
sudo apt upate && sudo apt upgrade
sudo apt install flatpak gnome-software-plugin-flatpak
```
Add flathub as a remote flatpaks repository for your user
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo --user
```

## Install and configure main applications

### Audio, image and video players and recorders
- Spotify for music streaming
- Peek for screen recording GIFs
- OBS Studio for screen and voice capture
- Amberoll to play offline music
```
flatpak install flathub com.spotify.Client com.uploadedlobster.peek  com.obsproject.Studio io.bassi.Amberol --user -y
```
### Audio, image and video editing tools
- Inkscape for vector drawing
- Draw IO for diagrams
- Color picker to pick colors

```
flatpak install flathub org.inkscape.Inkscape com.jgraph.drawio.desktop nl.hjdskes.gcolor3 --user -y
```
- Handbrake for compacting video files (optional)
- Piviti for simple video editing (optional)
```
flatpak install flathub fr.handbrake.ghb org.pitivi.Pitivi --user -y
```

### Communication tools
- Discord for friends chat
- Gnome Geary as an email client
- Feeds to read RSS feeds
- Zoom for video communication
```
flatpak install flathub com.discordapp.Discord org.gnome.Geary org.gabmus.gfeeds us.zoom.Zoom --user -y
```

### Web Browsers
- Google Chrome
```
flatpak install flathub com.google.Chrome --user -y
```
### Productivity
- Gnome Solanum: a pomodoro timer
- Getting Things Gnome: a to do list
- PDF Slicer to extract, merge and reorder PDFs
- Only Office as an Office Suite
- Visual Studio Code - a fully featured code editor
- Paper as a markdown based notes app
- Foliate as an E-book reader
```
flatpak install flathub org.gnome.Solanum org.gnome.GTG com.github.junrrein.PDFSlicer org.onlyoffice.desktopeditors com.visualstudio.code  io.posidon.Paper flatpak install flathub com.github.johnfactotum.Foliate --user -y
```
### Other tools
- Gnome Pika Backup for hard drive backups
- Bitwarden as a password management tool
- Authenticator as an OTP app
- Klavaro as a touch tiping tutor
- Almond as a virtual assistant
- Metadata cleaner
- Scans to PDF to add OCR funcionality and make PDFs searchable
```
flatpak install flathub org.gnome.World.PikaBackup com.bitwarden.desktop com.belmoussaoui.Authenticator net.sourceforge.Klavaro edu.stanford.Almond fr.romainvigier.MetadataCleaner com.github.unrud.djpdf --user -y
```
## Snap apps
- Authy as an OTP authenticator app with integration with Android (Can revoke android access)

First install snap
```
# if on debian based distro
sudo apt update
sudo apt install snapd
sudo snap install core

# if on fedora
sudo dnf install snapd
sudo ln -s /var/lib/snapd/snap /snap
```
Then install the app
```
sudo snap install authy
```

## Distribution repository apps
- Simple Scan for document scanning
```
# if on debian based distro
sudo apt install simple-scan

# if on fedora
sudo dnf install simple-scan
```

