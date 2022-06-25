# gnome-setup
Repository for command line script to setup environment.
Why in flatpak? To get the most up to date apps.

## Install and configure flatpak utilitary
Install flatpak utilitary if the distribution doesn't bring flatpaks by default
```
# If on Debian-based distributions
sudo apt upate && sudo apt upgrade
sudo apt install flatpak gnome-software-plugin-flatpak
```
Add flathub as a remote repository for flatpaks
```
# May not be necessary on Fedora
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

## Install and configure main applications

### Audio, image and video players and recorders
- Gnome Videos (Totem) as a video player
- Gnome Cheese to take photos
- Gnome Sound Recorder to record sounds
- Gnome Image Viewer as an Image Viewer
- Spotify for music streaming
- Peek for screen recording GIFs
- OBS Studio for screen and voice capture
- Video Downloader to get that youtube videos
- Amberoll to play offline music
```
flatpak install flathub org.gnome.Totem org.gnome.Cheese org.gnome.SoundRecorder org.gnome.eog com.spotify.Client com.uploadedlobster.peek  com.obsproject.Studio com.github.unrud.VideoDownloader io.bassi.Amberol --user
```
### Audio, image and video editing tools
- Inkscape for vector drawing
- Draw IO for diagrams
- Color picker to pick colors
- GIMP for image manipulation
- Handbrake for compacting video files
- Piviti for simple video editing
```
flatpak install flathub org.inkscape.Inkscape com.jgraph.drawio.desktop nl.hjdskes.gcolor3 org.gimp.GIMP fr.handbrake.ghb org.pitivi.Pitivi --user
```

### Communication tools
- Discord for friends chat
- Gnome Geary as an email client
- Feeds to read RSS feeds
```
flatpak install flathub com.discordapp.Discord org.gnome.Geary org.gabmus.gfeeds --user
```

### Web Browsers
- Google Chrome
```
flatpak install flathub com.google.Chrome --user
```
### Productivity
- Gnome Document Viewer (Evince)
- Gnome Calendar
- Gnome Solanum: a pomodoro timer
- Getting Things Gnome: a to do list
- PDF Slicer to extract, merge and reorder PDFs
- Only Office as an Office Suite
- Visual Studio Code - a fully featured code editor
- Paper as a markdown based notes app
```
flatpak install flathub org.gnome.Evince org.gnome.Calendar org.gnome.Solanum org.gnome.GTG com.github.junrrein.PDFSlicer org.onlyoffice.desktopeditors com.visualstudio.code  io.posidon.Paper --user
```
### Other tools
- Bitwarden as a password management tool
- Authenticator as an OTP app
- Klavaro as a touch tiping tutor
- Almond as a virtual assistant
```
flatpak install flathub com.bitwarden.desktop com.belmoussaoui.Authenticator net.sourceforge.Klavaro edu.stanford.Almond --user
```

