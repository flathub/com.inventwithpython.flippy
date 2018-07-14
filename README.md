# Flippy packaging: example for using Flatpak with Pygame

This is the Flatpak information for a simple Python game called **Flippy**.
You can see the packaged result here:
https://flathub.org/apps/details/com.inventwithpython.flippy

Flippy is a real game, but it's also here as an example for how to package
a game based on [Pygame](https://www.pygame.org/news). Feel free to copy
these files and modify them to package other games. Formally, the packaging
metadata in this repository is CC0 licensed, making it totally free to reuse,
while the game itself is under a BSG license.

So what are all these files?

- [`com.inventwithpython.flippy.json`](https://github.com/flathub/com.inventwithpython.flippy/blob/master/com.inventwithpython.flippy.json)
  is the Flatpak 'manifest' that tells Flatpak how to build the game.
  See [manifests in the Flatpak docs](http://docs.flatpak.org/en/latest/manifests.html).
  - `shared-modules` is a Git submodule which contains instructions for building
    pygame and its dependencies.
- [`launch.py`](https://github.com/flathub/com.inventwithpython.flippy/blob/master/launch.py)
  is a Python wrapper script which runs the game.
- [`com.inventwithpython.flippy.desktop`](https://github.com/flathub/com.inventwithpython.flippy/blob/master/com.inventwithpython.flippy.desktop)
  is a 'desktop entry' file that will show the game in your application menu or launcher.
  - The three `icon_*.png` files are the icons it will use in different sizes.
- [`com.inventwithpython.flippy.appdata.xml`](https://github.com/flathub/com.inventwithpython.flippy/blob/master/com.inventwithpython.flippy.appdata.xml)
  contains the 'Appstream' metadata which describes the application in
  software centres and on the Flathub website. See
  [the Appstream docs](https://www.freedesktop.org/software/appstream/docs/index.html)
  for more about this.

You've probably noticed that several files have long names starting with
`com.inventwithpython.flippy`.
This is the game's *application ID*, which is very important for Flatpak.
It's based on reversing a domain name that the author controls (in this case,
[inventwithpython.com](https://inventwithpython.com/)).
This makes a unique name, even if there is another application called 'Flippy'.
