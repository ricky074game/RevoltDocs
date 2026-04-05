---
icon: material/skull
---

# Inside Game Folder

When you play certain modified or offline (pirated) Steam games, the emulator or crack saves your achievement progress directly into the folder where the game is installed (usually right next to the game executable in a folder called steam_setting).

The **Inside Game Folder** tracking mode is used to tell RevoltUltimate to look *inside* the local game directory for those achievement changes.

---

## How to Add a Game

1. Click the **`+` (Plus) button** located on the top bar of the main RevoltUltimate window.
2. Search for the game you want to add and double click it to add it.
3. Select the folder in which the game is installed.

RevoltUltimate will now actively watch this directory for files like `achievements.json` or `.ini` config files to track your unlocks!

---

## Something went wrong?

??? question "Can't find the achievements.json or achievements.ini anywhere?"
    Make sure you at least start the game once (you can just go to the main menu and then close it) before you try searching for the achievements. Also, make sure that your crack supports achievements (most do, but i dont know if any custom ones support it as well). If you cant actually find it, or you notice it saves the achievements outside, then go to Outside Game Folder instead to add the game.

??? question "Achievement isn't given when it is supposed to?"
    First, ensure that this isnt a bug with the game itself. The game can be broken with achievements and I have no way to fix that. If that is not the case, and you notice that the file is actually changing, this is a bug and needs to be actually reported to the developer with github issues.
