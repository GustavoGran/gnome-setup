# linux-mint-setup
Repository for command line script to setup environment.
Why in flatpak? To get the most up to date apps.`

## Remove default apps that come with Mint and will not be used
- Rhythmbox
```
sudo apt purge -y rhythmbox
```
## Install core system repo apps
Make sure your current apps and dependencies are updated
```
sudo apt update
```
Then upgrade them
```
sudo apt upgrade -y
```

## Install NVIDIA graphics drivers

Do it through the driver management visual tool, it is much easier that way

## Reboot to fix changes

```
reboot
```

## Install and configure flatpak utilitary
Install flatpak utilitary if the distribution doesn't bring flatpaks by default
```
# If on Debian-based distributions
sudo apt install flatpak gnome-software-plugin-flatpak
```
Add flathub as a remote flatpaks repository for your user
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo --user
```

## Install and configure main applications

### Misc
- Spotify for music streaming
- Peek for screen recording GIFs
- OBS Studio for screen and voice capture
- Amberoll to play offline music
- Inkscape for vector drawing
- Color picker to pick colors
- Handbrake for compacting video files (optional)
- Discord for friends chat

```
flatpak install flathub com.spotify.Client com.uploadedlobster.peek  com.obsproject.Studio io.bassi.Amberol org.inkscape.Inkscape nl.hjdskes.gcolor3 fr.handbrake.ghb com.discordapp.Discord --user -y
```

### Web Browsers
- Chrome
- Firefox
  
```
flatpak install flathub com.google.Chrome org.mozilla.firefox --user -y
```
### Productivity
- Gnome Solanum: a pomodoro timer
- Getting Things Gnome: a to do list
- PDF Slicer to extract, merge and reorder PDFs
- Only Office as an Office Suite
- Visual Studio Code - a fully featured code editor
- Paper as a markdown based notes app
- Foliate as an E-book reader
- Bitwarden as a password management tool
- Authenticator as an OTP app
- Klavaro as a touch tiping tutor
- Scans to PDF to add OCR funcionality and make PDFs searchable
```
flatpak install flathub org.gnome.Solanum org.gnome.GTG com.github.junrrein.PDFSlicer org.onlyoffice.desktopeditors com.visualstudio.code  io.posidon.Paper com.github.johnfactotum.Foliate com.bitwarden.desktop com.belmoussaoui.Authenticator net.sourceforge.Klavaro com.github.unrud.djpdf --user -y
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
sudo apt install simple-scan gimp -y

# if on fedora
sudo dnf install simple-scan
```

## Set the US Intl keyboard
[https://github.com/raelgc/win_us_intl/](https://github.com/raelgc/win_us_intl/)
[https://askubuntu.com/questions/875688/how-to-install-usa-international-keyboard-option-on-ubuntu-gnome-16-10](https://askubuntu.com/questions/875688/how-to-install-usa-international-keyboard-option-on-ubuntu-gnome-16-10)
[https://forums.linuxmint.com/viewtopic.php?t=329552](https://forums.linuxmint.com/viewtopic.php?t=329552)

## Setup for gaming
[https://diolinux.com.br/games/aprenda-deixar-o-ubuntu-e-o-linux-mint.html](https://diolinux.com.br/games/aprenda-deixar-o-ubuntu-e-o-linux-mint.html)
Se você pretende usar o Steamplay, só a instalação dos drivers adequado já deve ser o suficiente, porém, se deseja utilizar uma ferramenta como o Lutris para rodar games de outras lojas, ainda que o Lutris se encarregue de fazer todos os ajustes geralmente, para aumentar o nível de compatibilidade é possível instalar alguns complementos ao Wine nativo do seu sistema.   Primeiro precisamos habilitar o suporte para arquitetura de 32 bits, isso é fácil de fazer vamos abrir o terminal e digitar (ou colar) o seguinte comando:  
```
sudo dpkg --add-architecture i386
```
Agora vamos instalar o Wine-Stable pelo Synaptic e procurar por esses pacotes lá:   **wine-stable (3.0-1ubuntu1) ; libwine (3.0-1ubuntu1) ; libwine-development (3.6-1) ; wine64 (3.0-1ubuntu1) ; wine64-development (3.6-1) ; wineprefix e fonts-wine**   No caso do Linux Mint, você também pode procurar diretamente na loja de aplicativos, não precisando do Synaptic necessariamente, no Ubuntu, obrigatoriamente será necessário usar o Synpatic, ou então usar o terminal para instalar cada um dos pacotes usando o “apt”.Agora vamos conferir se os pacotes do Vulkan estão instalados, se você estiver usando Nvidia, ao instalar o driver, o suporte à Vulkan é ativado, não sendo necessário outras medidas.

