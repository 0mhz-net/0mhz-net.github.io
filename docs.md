---
title: 0MHz DOS Collection Setup
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
