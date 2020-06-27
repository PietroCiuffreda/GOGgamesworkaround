**GOG games workaround**

This is a manual workaround for GOG games that don't work on Linux systems. I don't know if this is could be a temporary solution or a definitive one, but it works for many games and applications that requires a library or libraries that are not installed on.

For example, I'd like to install the game "Generic Game" after buying it in the GOG store. After downloading the .sh file and install it, it crashes and the log says:

`libxxxxx.0 no such file or directory  (generic library/libraries missing)`

My workaround consists in downloading `libxxxxx.0.deb or rpm` on the official repositories, compiling them (solving also its dipendences, because sometimes), then extracting and copying the `libxxxx.0.lib` file it in the `/lib` directory; after this creating a new script file called `script.sh` like this:

```
#!/bin/bash
LD_LIBRARY_PATH=/lib/ ./start.sh
```
then saving it in the game's directory; in this way, launching the game through this new script, it should work.
Also, if you want to make this workaround working also for the menu icon, then you should edit the `/home/user/.local/share/applications/gog_com-Gamefile.desktop` adding or editing the `[Exec]` line with the new script's path, just like this:
```[Desktop entry]
.
.
.
Exec="/home/user/GOG Games/Generic Game/script.sh"
```

If you have suggestions or betters workaround please suggest me them or add them here.


**Pietro Ciuffreda
Lubuntu 20.04 LTS**


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0
International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
