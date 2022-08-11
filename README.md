# mpv-config

![mpv logo](https://raw.githubusercontent.com/mpv-player/mpv.io/master/source/images/mpv-logo-128.png)

## Overview

**mpv** is a free (as in freedom and free beer), open-source, and cross-platform media player. It supports
a wide variety of media file formats, audio and video codecs, and subtitle types.

This is my setup of MPV alongside scripts that I use. Before installing, read this whole README to learn how to exactly install it.

## Installation (on Windows)
Here are the steps to install mpv and to use my configuration files on Windows:
* Download the latest 64bit mpv Windows build by shinchiro from [mpv.io/installation](https://mpv.io/installation/) and extract it wherever you please. This is now your mpv folder
* Run `mpv-install.bat` as administrator, which is located in `installer` folder
* To download this configuration, press `CODE`, then `Download ZIP`. (Might add zip in release tab) Extract it and put it next to mpv.exe in a folder called `portable_config`

After following the steps above, your mpv folder should look like this (Windows only for now):

```
├── doc
│   ├── manual.pdf
│   └── mpbindings.png
│
├── installer
│   ├── configure-opengl-hq.bat
│   ├── mpv-icon.ico
│   ├── mpv-install.bat                       # Run this with administrator priviledges to install mpv
│   ├── mpv-uninstall.bat                     # Run this with administrator priviledges to uninstall mpv
│   └── updater.ps1
│
├── mpv
│   └── fonts.conf
│
├── portable_config                           # This is where this repository goes
│   ├── fonts
│   │   └── Material-Design-Iconic-Font.ttf   # Buttons and etc. for ModernX Script to Work
│   │
│   ├── scripts
│   │   ├── autoload.lua                      # Script to automatically load a video after the first one ends
│   │   ├── cycle-profile.lua                 # Cycle through profiles (For future because I plan to make multiple profiles)
│   │   ├── mordenx.lua                       # Script for modern UI
│   │   └── seek-to.lua                       # Script that allows to seek to an absolute position in the current video by typing its timestamp.
│   │
|   ├── shaders
│   │   ├── ACNet
│   │   │   └── ACNet.glsl
│   │   ├── AMD
│   │   │   ├── CAS.glsl
│   │   │   ├── CAS-scaled.glsl
│   │   │   └── FSR.glsl
│   │   ├── Anime4k (All of the files glsl's from the repository)
│   │   ├── FSRCNNX
│   │   │   └── FSRCNNX_x2_8-0-4-1.glsl
│   │   ├── Krig
│   │   │   └── KrigBilateral.glsl
│   │   └── SSim
│   │   │   └── SSimDownscaler.glsl
│   │
│   ├── input.conf                            # Keybinding configuration
│   └── mpv.conf                              # MPV's main configuration file
│
├── d3dcompiler_43.dll
├── mpv.com
├── mpv.exe                                   # The mpv executable file
└── updater.bat                               # Run this with administrator priviledges to update your mpv to the latest version
```

## Scripts
* [Autoload](https://github.com/shazzaam7/mpv-config/blob/windows/scripts/autoload.lua) —
  [Source](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)\
  Automatically load playlist entries before and after the currently playing file, by scanning the directory.
  
* [Cycle Profile](https://github.com/shazzaam7/mpv-config/blob/windows/scripts/cycle-profile.lua) —
  [Source](https://github.com/CogentRedTester/mpv-scripts#cycle-profile)\
  Cycles through a list of profiles sent via a script message and prints the profile-desc to the OSD. More details at the top of the file.
  
* [ModernX](https://github.com/shazzaam7/mpv-config/blob/windows/scripts/mordenx.lua) —
  [Source](https://github.com/cyl0/mpv-osc-morden-x)\
  A modern OSC UI replacement for MPV that retains the functionality of the default OSC.

* [MPV-webm](https://github.com/ekisu/mpv-webm) — [Source](https://github.com/ekisu/mpv-webm)
  
* [Seek To](https://github.com/shazzaam7/mpv-config/blob/windows/scripts/seek-to.lua) —
  [Source](https://github.com/dexeonify/mpv-config/blob/main/scripts/seek-to.lua)\
  Seek to an absolute timestamp specified via keyboard input or pasted from clipboard.

## Shaders

The shaders included in the `shaders` folder:

* [Anime4K v4.0.1 Stable](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/Anime4K) — [Source](https://github.com/bloc97/Anime4K)\
  Used for upscaling anime. (CTRL + [1-6] To change Anime4K [modes](https://github.com/bloc97/Anime4K/blob/815b122284304e6e1e244a8cf6a160eeaa07040c/GLSL_Instructions.md#modes))

* [ACNetGLSL](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/ACNet) - [Source](https://github.com/TianZerL/ACNetGLSL)
  Another upscaler. Alternative to Anime4K. I only used the default one because it looked the best in my testing.

* [AMDFSR](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/AMD) - [Source](https://gist.github.com/agyild/82219c545228d70c5604f865ce0b0ce5)
  AMD FidelityFX Super Resolution. Enabled by default. Edited Line 38 from 1.0 to 0.5.

* [AMDCAS](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/AMD) - [Source](https://gist.github.com/agyild/bbb4e58298b2f86aa24da3032a0d2ee6)
  AMD FidelityFX Contrast Adaptive Sharpening. Enabled by default alongside FSR.

* [FSRCNNX](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/FSRCNNX) - [Source](https://github.com/igv/FSRCNN-TensorFlow)
  Used for luma upscaling.

* [KrigBilateral](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/Krig) - [Source](https://gist.github.com/igv/a015fc885d5c22e6891820ad89555637)
  Used for chroma upscaling and downscaling. Enabled by default alongside FSR and CAS.
  
* [SSimDownscaler](https://github.com/shazzaam7/mpv-config/tree/windows/shaders/SSim) - [Source](https://gist.github.com/igv/36508af3ffc84410fe39761d6969be10)
  Used for luma downscaling.
  
## Useful Links

* [MPV Manual](https://mpv.io/manual/master/)\
  Extremely useful for knowing what certain options do and what to put in `mpv.conf`
* [MPV User Scripts](https://github.com/mpv-player/mpv/wiki/User-Scripts)\
  Compilation of useful community-published scripts to be used with mpv
* [mpv.conf guide](https://iamscum.wordpress.com/guides/videoplayback-guide/mpv-conf/) by iamscum
* [MPV Configuration Guide for Watching Videos](https://kokomins.wordpress.com/2019/10/14/mpv-config-guide/) by Kokomins
* [Noelsimbolon's repo for his MPV configuration](https://github.com/noelsimbolon/mpv-config)
  Nice documentation of his configuration and repository. Can learn a lot for making your own repository about your MPV configuration

## Official Links

* [mpv homepage](https://mpv.io/)  
* [mpv wiki](https://github.com/mpv-player/mpv/wiki)
* [mpv FAQ](https://github.com/mpv-player/mpv/wiki/FAQ)
* [mpv manual](https://mpv.io/manual/master/)
