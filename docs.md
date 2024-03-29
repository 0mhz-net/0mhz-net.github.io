---
title: ⓿MHz DOS Collection Setup
--- 

### Setting up a single game

Every game setup is standalone, and contains the files needed to get it running on MiSTer.

* Simply unpack the zip for the game you want, the file structure will look something like this:

```
_DOS Games/
  Super Cars International.mgl
config/
  AO486.CFG
games/
  ao486/
    media/
      super cars international/
        [hard drive images go here]
```

* Copy these files and folders to the root of your MiSTer SD card (use the "Replace Files" or "Merge" option if your OS asks to overwrite the config files). 

(Obviously, make a backup copy of your `AO486.CFG` file if you already have a setup you want to keep.)

### Starting the game

Once the files have been copied over, 

* Boot up your MiSTer.
* You will see a new, top-level `DOS Games` section in the menu, select it.
* Select the game you want to start playing.
* The game will boot with the default settings for graphics and sound, including any memory managers or drivers needed.

### Setting up multiple games at once

If you are trying to add multiple games to your system all in one go, the process is very similar:

* Unpack all the zip files **to the same folder** — often shown as "Extract Here" or a similar option, depending on which unpacking application you are using. Also, when asked, "Replace All", since the config file is the same for every game, but it is included to make sure the game also works stand-alone.
* The structure should then look something like this:

```
_DOS Games/
  First Game.mgl
  Second Game.mgl
  Third Game.mgl
config/
  AO486.CFG
games/
  ao486/
    media/
      first game/
        [hard drive images go here]
      second game/
        [hard drive images go here]
      third game/
        [hard drive images go here]

```
* Copy these files and folders to the root of your MiSTer SD card. The `.cfg` file is the same for every game, so there will only be one once you have unpacked all the games.

## Other questions

### Can I use the `ao486` core with just a gamepad/joystick setup?

While we aim to make it as simple as possible to use the 0MHz DOS Collection usable with only controllers, the PC DOS era is a little bit of a wild west when it comes to joystick and controller setups. We recommend that you have a mouse and keyboard available while using this core on MiSTer.

### Can I run the DOS games on a 15kHz CRT TV or monitor?

Yes, you can use the scaler to output a 15kHz signal that should work on consumer TVs and PVMs/BVMs, but do note that some games may be too high resolution for e.g. text to be readable. Also, not all CRTs will be able to handle this, but we have seen success with the below settings on several CRTs.

Add the following to your `MiSTer.ini`:

```
[ao486]
direct_video=0
vga_scaler=1
vsync_adjust=1
vscale_mode=3
video_mode=1440,40,136,176,240,3,10,6,27000
```

Make sure to set Aspect Ratio to Full Screen in Audio and Video Section of the core.

You can play around with the values a little to improve centering on your particular display. The three values are horizontal front porch (`40`), sync (`136`) and back porch (`176`), which control the width and centering of the picture. Adjusting vertical sync is a lot trickier and you won't have as much room to play with.

(Thanks to Christoph Helms for these settings! If you want more detail or other settings, check out the [forum thread](https://misterfpga.org/viewtopic.php?p=63332#p63332))

### Should I worry about PC/DOS viruses?

In short: No. 

Viruses on the PC were quite common, and some retail games even shipped with infected disks in the box. 

Even though we don't control what's being used as inputs to the script that creates the 0MHz DOS Collection setup, pretty much all games and demos run inside VHD containers, you can think of them as "virtualization for DOS". Their job is to insulate the game from the rest of the system, reset CPU vectors, and other system state preservation. So even if a game or demo contains a virus, it cannot stay resident in memory, and will not spread to the rest of the system outside of the sandbox it has been given. Whenever you switch to a new game, the core does a cold boot, and nothing survives.

If you want to check the state of a given setup you downloaded from the internet, use your favorite antivirus tool. But unless you try to mount old hard drive images and start these games on your Windows PC, there is no way to contract a virus on your system. Most antivirus software is generally of poor quality, and false positives are not uncommon, but also nothing to worry about.

We check all files that are under our control for viruses before release.

