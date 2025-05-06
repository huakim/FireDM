Homepage :https://github.com/huakim/FireDM.git

![GitHub All Releases](https://img.shields.io/github/downloads/huakim/firedm/total?color=blue&label=GitHub%20Releases)

![GitHub issues](https://img.shields.io/github/issues-raw/huakim/firedm?color=blue) - ![GitHub closed issues](https://img.shields.io/github/issues-closed-raw/huakim/firedm?color=blue)

![logo](https://github.com/huakim/FireDM/blob/master/icons/48x48.png)
FireDM is a python open source (Internet Download Manager) 
with multi-connections, high speed engine, 
it downloads general files and videos from youtube and tons of other streaming websites . <br>
Developed in Python, based on "LibCurl", and "youtube_dl".

[**Download Latest version**](https://github.com/huakim/FireDM/releases/latest)

---
**Features**:
* High download speeds "based on LibCurl"
* Multi-connection downloading "Multithreading"
* Automatic file segmentation.
* Automatic refresh for dead links.
* Resume uncompleted downloads.
* Support for Youtube, and a lot of stream websites "using youtube-dl to fetch info and libcurl to download media".
* download entire video playlist or selected videos.
* download fragmented video streams, and encrypted/nonencrypted HLS media streams.
* watch videos while downloading* "some videos will have no audio until
  finish downloading".
* download video subtitles.
* write video metadata to downloaded files.
* check for application updates.
* Scheduling downloads
* Re-using existing connection to remote server.
* Clipboard Monitor.
* proxy support (http, https, socks4, and socks5).
* user/pass authentication, referee link, use cookies, video thumbnail,
  subtitles.
* use custom cookies files.
* MD5 and SHA256 checksums.
* Custom gui themes.
* Set download Speed limit
* User can run shell commands or shutdown computer on download completion.
* Control number of Concurrent downloads and Max. connections per each download.

---
# How to use FireDM:
running in command line: show help by typing `firedm -h`  <br>

running GUI: Refer to user guide at https://github.com/firedm/FireDM/blob/master/docs/user_guide.md

----------------------
## Manually installing FireDM with pip (Linux):
1- check python version (minimum version required is 3.6): `python3 --version`

2- install required packages first:<br>
- Linux, ubuntu:<br>
```sh
sudo apt install ffmpeg libcurl4-openssl-dev libssl-dev python3-pip python3-pil python3-pil.imagetk python3-tk python3-dbus gir1.2-appindicator3-0.1
sudo apt install fonts-symbola fonts-linuxlibertine fonts-inconsolata fonts-emojione
```

3- install firedm using pip:<br>

```sh
python3 -m pip install firedm --user --upgrade --no-cache
```

## Running from source code inside virtual environment (Linux):
1- check python version (minimum version required is 3.6): `python3 --version`

2- install required packages first:<br>
- Linux, ubuntu:<br>
```sh
sudo apt install ffmpeg libcurl4-openssl-dev libssl-dev python3-pip python3-pil python3-pil.imagetk python3-tk python3-dbus gir1.2-appindicator3-0.1
sudo apt install fonts-symbola fonts-linuxlibertine fonts-inconsolata fonts-emojione
```

3- run below code to clone this repo, create virtual environment, install requirements, create launch script, and finally run FireDM

```sh
git clone --depth 1 https://github.com/huakim/FireDM.git
python3 -m venv ./.env
source ./.env/bin/activate
python3 -m pip install -r ./FireDM/requirements.txt
echo "source ./.env/bin/activate
python3 ./FireDM/firedm.py \$@
" > firedm.sh
chmod +x ./firedm.sh
./firedm.sh
```

> optionally create .desktop file and add FireDM to your applications
```sh
FireDMLSPATH=$(realpath ./firedm.sh)
echo "[Desktop Entry]
Name=FireDM
GenericName=FireDM
Comment=FireDM Download Manager
Exec=$FireDMLSPATH
Icon=firedm
Terminal=false
Type=Application
Categories=Network;
Keywords=Internet;download
" > FireDM.desktop
cp ./FireDM.desktop ~/.local/share/applications/
mkdir -p ~/.local/share/icons/hicolor/48x48/apps/
cp ./FireDM/icons/48x48.png ~/.local/share/icons/hicolor/48x48/apps/firedm.png
```

## Arch-linux (AUR):
 - Firedm available for arch linux on AUR https://aur.archlinux.org/packages/firedm/ , Special Thanks to qontinuum for maintaining this package.

---

# Known Issues:
- systray icon: depends on Gtk+3 and AppIndicator3 on linux, please refer to your distro guides on how to install these packages if you need systray to run properly
---

# Dependencies:
- Python 3.6+: tested with python 3.6 on windows, and 3.7, 3.8 on linux
- tkinter
- [ffmpeg](https://www.ffmpeg.org/) : for merging audio with youtube DASH videos "it will be installed automatically on windows"

    ```
    ttf-linux-libertine 
    ttf-inconsolata 
    ttf-emojione
    ttf-symbola
    noto-fonts
    ```
- [pycurl](http://pycurl.io/docs/latest/index.html): is a Python interface to libcurl / curl as our download engine,
- [youtube_dl](https://github.com/ytdl-org/youtube-dl): famous youtube downloader, limited use for meta information extraction only but videos are downloaded using pycurl
- [yt_dlp](https://github.com/yt-dlp/yt-dlp): a fork of youtube-dlc which is inturn a fork of youtube-dl
- [certifi](https://github.com/certifi/python-certifi): required by 'pycurl' for validating the trustworthiness of SSL certificates,
- [plyer](https://github.com/kivy/plyer): for systray area notification.
- [awesometkinter](https://github.com/Aboghazala/AwesomeTkinter): for
  application gui.
- [pillow](https://python-pillow.org/): imaging library for python
- [pystray](https://github.com/moses-palmer/pystray): for systray icon

**Note for pycurl:** <br>
for windows users who wants to run from source or use pip:
unfortunately, pycurl removed binary versions for windows and this link "https://dl.bintray.com/pycurl/pycurl/" is now dead, and one has to build pycurl from source which is not an easy task, details are here http://pycurl.io/docs/latest/install.html#windows
normal pip install i.e `python -m pip install pycurl` probably will fail on windows, your best choice is to use FireDM standalone/portable exe version.


for linux users:
there is no issues, since most linux distros have curl preinstalled, so pycurl will link with libcurl library to get built with no issues, checked with python versions 3.6, 3.7, and 3.8 working with no problems.
<br>


---
# what is the benefit of open source, compared to closed-source/Proprietary software if both are free?
As said, **"if the product is free, then you are the product"**, most
free closed-source software collect data about you, some of them are
toxic and plant trojans/spy-wares in your system, with open source,
nothing hidden, and source code exposed to thousands of programmers, no
one can play dirty games.


Need to mention, this project is never made to compete with other
download managers, it is just a "hopefully useful" addition.

---

<br>

# How to contribute to this project:
1- by testing the application and opening
[new issue](https://github.com/huakim/FireDM/issues/new) for bug
reporting, feature request, or suggestions.  
2- check
[developer guidelines](https://github.com/huakim/FireDM/blob/master/docs/developer_guide.md).  
3- check
[todo list](https://github.com/huakim/FireDM/blob/master/todo.md).  
4- check open issues, see if you can help.  
5- fork this repo and pull request

<br>

---

# Some articles/reviews on this project*:
- [ghacks](https://www.ghacks.net/2020/08/13/pyidm-is-an-open-source-download-manager-that-can-download-videos-and-playlists/)
- [softpedia](https://www.softpedia.com/get/Internet/Download-Managers/PyIDM.shtml)
- [hackermilk](http://hackermilk.info/2020/01/an_open_source_alternative_to_internet.html)
---

# contributors:
Please check
[contributors.md](https://github.com/huakim/FireDM/blob/master/contributors.md)
for a list of contributors

---

# Feedback:
your feedback is most welcomed by filling a
[new issue](https://github.com/huakim/FireDM/issues/new)  
or email to: info.pyidm@gmail.com <br>


---

Author:  
Mahmoud Elshahat  
2019-2022
huakim
2025

