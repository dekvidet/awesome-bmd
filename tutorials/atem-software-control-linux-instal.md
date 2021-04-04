# Install ATEM Software Control on Linux

## Verified Distros

- Ubuntu 16.04 LTS
- Kubuntu 18.04 LTS
- Kubuntu 20.04 LTS

## Installation Guide

[Watch the video version of this guide on YouTube]()

### Download and Install 3rd Party Software

Enable 32 bit architecture:

    sudo dpkg --add-architecture i386

Install latest Wine with Winetricks, Mono and SDL2 backport
    
    wget -qO - https://dl.winehq.org/wine-builds/winehq.key | sudo apt-key add -
    sudo add-apt-repository ppa:cybermax-dexter/sdl2-backport
    sudo apt-add-repository "deb https://dl.winehq.org/wine-builds/ubuntu $(lsb_release -cs) main"
    sudo apt-get update
    sudo apt install --install-recommends winehq-stable winetricks mono-complete

Create the Wine environment that we will use (every popup coming up can be closed):

    env WINEPREFIX=~/.wine64 WINEARCH=win64 winecfg

### Install ATEM Software Control Under Wine

Download latest software for Windows from [Blackmagic Design's Support Page](https://www.blackmagicdesign.com/support/family/atem-live-production-switchers). Extract it, and get the path for the "Install Atem" .msi file. In our example it will be `~/Downloads/Install\ ATEM\ v8.1.2.msi `. Now run the installer in our Wine environment then click _Next_ **until you get to the end of the installer** where it tells you that "the setup wizzard ended prematurely".

    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 msiexec /i ~/Downloads/Install\ ATEM\ v8.1.2.msi 

At this point, everything is installed, but since the installer failed, if you click _Finish_ it will undo everything it did, so we need to copy all the files created by the installer to a temporary directory (you can do these steps by hand too):

    cp -r ~/.wine64/drive_c/Program\ Files\ \(x86\)/Blackmagic\ Design ~/.

Now click _Finish_ on the installer then move the files back from the temporary directory to their original place:
    
    mv ~/Blackmagic\ Design ~/.wine64/drive_c/Program\ Files\ \(x86\)/
    
Install a DLL the installer left out:

    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 regsvr32 ~/.wine64/drive_c/Program\ Files\ \(x86\)/Blackmagic\ Design/Blackmagic\ ATEM\ Switchers/BMDSwitcherAPI64.dll

Disable sound to fix an issue that causes the ON/AFV buttons of the audio mixer blink rapidly both in the software and on the phisical switcher itself.

    env WINEPREFIX=~/.wine64 WINEARCH=win64 winetricks sound=disabled

Installation is done. You can run the .exe trought the wine environment:

    env WINEPREFIX=~/.wine64 WINEARCH=win64 taskset -c 0 wine64 ~/.wine64/drive_c/Program\ Files\ \(x86\)/Blackmagic\ Design/Blackmagic\ ATEM\ Switchers/ATEM\ Software\ Control/ATEM\ Software\ Control.exe

You can run the ATEM Setup as well, but keep in mind that even tho it recognizes a switcher plugged via USB, it can only change settings trough ethernet, so you can't change network settings or update firmware. For this you still have to use Windows.

    env WINEPREFIX=~/.wine64 WINEARCH=win64 taskset -c 0 wine64 ~/.wine64/drive_c/Program\ Files\ \(x86\)/Blackmagic\ Design/Blackmagic\ ATEM\ Switchers/ATEM\ Setup/ATEM\ Setup.exe 

### Adding a Desktop Shortcut
    
For ease of use, you should create a desktop shortcut for this lengthy command. This process is diferent for every desktop environment. We will list a few tutorials. Keep in mind, that **every path in the command has to be absolute** starting from root, for example:

    env WINEPREFIX=/home/superuser/.wine64 WINEARCH=win64 taskset -c 0 wine64 /home/superuser/.wine64/drive_c/Program\ Files\ \(x86\)/Blackmagic\ Design/Blackmagic\ ATEM\ Switchers/ATEM\ Software\ Control/ATEM\ Software\ Control.exe

Desktop shortcut tutorials for different distros:
    
- [Ubuntu 18.04](https://linuxconfig.org/how-to-create-desktop-shortcut-launcher-on-ubuntu-18-04-bionic-beaver-linux)
- [Ubuntu 20.04](https://linuxconfig.org/how-to-create-desktop-shortcut-launcher-on-ubuntu-20-04-focal-fossa-linux)
- Kubuntu: _Right Click on Launcher > Edit Applications > New Item_

## Resources Used

- https://forum.blackmagicdesign.com/viewtopic.php?f=4&t=93169

## Troubleshooting

### Top Menu Not Working

If the top menu doesn't work you might be able to solve this by configuring Wine:

    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 winecfg

On the _Graphics_ tab check _Emulate a virtual desktop_ and set a preferred desktop size. The drawback of this workaround is that you won't be able to resize the window.

### Problems With Wine Libraries

If you have problems with installing Wine libraries you can download them here:

- Wine Mono: https://dl.winehq.org/wine/wine-mono/4.8.3/wine-mono-4.8.3.msi
- Wine Gecko: https://dl.winehq.org/wine/wine-gecko/2.47/wine_gecko-2.47-x86_64.msi

Then install them manually:

    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 explorer

Open _My Computer > Control Panel > Add/Remove Programs_ then install Mono and Gecko.

### Installation for legacy systems

    sudo add-apt-repository universe
    sudo add-apt-repository multiverse
    sudo dpkg --add-architecture i386
    sudo apt-get update
    sudo apt-get -y install wine64 wine32 winetricks cabextract mono-complete

    env WINEPREFIX=~/.wine64 WINEARCH=win64 winecfg
    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 msiexec /i install-packages/wine-mono-4.8.3.msi
    env WINEPREFIX=~/.wine64 WINEARCH=win64 wine64 msiexec /i install-packages/wine_gecko-2.47-x86_64.msi
    env WINEPREFIX=~/.wine64 WINEARCH=win64 winetricks -q vcrun2013 allfonts
