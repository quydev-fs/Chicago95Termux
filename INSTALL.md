# Chicago95 Theme Installation for Termux (with XFCE/Termux:X11)
These instructions assume you have a working Termux environment and have set up a VNC server running a graphical desktop environment like XFCE.

## Step 1: Get the XFCE environment

### A. Update / Upgrade

```bash
pkg update -y
pkg upgrade -y
```
### B. Setup X11 and TUR
```bash
pkg install x11-repo tur-repo -y
```
### C. Basic Dependencies
```bash
pkg install termux-x11-nightly pulseaudio xfce4 git -y
```
### D. Startup script
[Here is it!](Extras/start.sh)

## Step 2: Clone the repo
```bash
git clone https://github.com/quydev-fs/Chicago95Termux.git
```

## Step 3: Directory setup
```bash
mkdir ~/.themes
mkdir ~/.icons
mkdir -p ~/.fonts/truetype # or ~/.local/share/fonts/truetype
mkdir -p ~/.local/share/xfce4/terminal/colorschemes
mkdir -p ~/.config/xfce4/terminal/
```
## Step 4: Install the theme
```bash
cp -aR ~/Chicago95Termux/Theme/* ~/.themes
cp -aR ~/Chicago95Termux/Icons/* ~/.icons
cp -aR ~/Chicago95Termux/Cursors/* ~/.icons
cp -aR ~/Chicago95Termux/Fonts/* ~/.fonts/truetype # or ~/.local/share/fonts/truetype
cp -aR ~/Chicago95Termux/Extras/Chicago95.theme ~/.local/share/xfce4/terminal/colorschemes/
cp -aR ~/Chicago95Termux/Extras/terminalrc ~/.config/xfce4/terminal/terminalrc
```
## Step 5: Start XFCE and set the theme in terminal
Remember to start xfce before go to this step
```bash
. ~/Chicago95Termux/start.sh
```
### A. In xfce-terminal
```bash
xfconf-query -c xsettings -p /Net/ThemeName -s "Chicago95"
xfconf-query -c xfwm4 -p /general/theme -s "Chicago95"
xfconf-query -c xsettings -p /Net/IconThemeName -s "Chicago95"
xfconf-query -c xsettings -p /Gtk/FontName -s "More Perfect DOS VGA Regular 10"
xfconf-query -c xsettings -p /Xft/Monospace -s "More Perfect DOS VGA 10"
```
### B. the GUI method
goto Applications > Settings > Appearance and set the theme/icons to Chicago95, font to "More Perfect DOS VGA Regular 10"
