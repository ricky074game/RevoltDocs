---
icon: material/skull
---

# Outside Game Folder

Certain Steam cracks or emulators prefer to keep the game installation directory completely clean. Instead of saving achievements where the game is installed, they store them "Outside the Game Folder", usually in your Windows user profile (like `AppData` or `Public Documents`).

The **Outside Game Folder** tracking mode tells RevoltUltimate to monitor these external Windows directories in order to find the achievements for this game.

---

## How to Add a Game

The game should usually be populated automaically if it uses one of the common cracks and stores its file in one of the common folders located. However, if you think that is not the case and the game does not show up automatically.

1. Go to **Settings** in RevoltUltimate.
2. Navigate to the **Folders** section.
3. Add the folder where the achievement for the game is stored for that specific crack. Try to find a file called either achievements.json or achievements.ini  (You might need to research where your specific crack stores its achievement files, or feel free to ask the community for help).

!!! info "Note"
    While not mandatory, it is strongly recommended to add the parent folder containing the achievement files rather than selecting the specific file itself. THis way if you use the same crack for another game, it will automatically be added.

---

## Something went wrong?

??? question "Can't find the achievements.json or achievements.ini anywhere?"
    Make sure you at least start the game once (you can just go to the main menu and then close it) before you try searching for the achievements. Also, make sure that your crack supports achievements (most do, but i dont know if any custom ones support it as well)

??? question "The game is found but no achievements are there?"
    The game is found, but no achievements show up? Please wait a moment. If you have inputted a Steam Web API key, it will attempt to fetch and sync the achievements using it, which will update shortly. If no key is provided, the backup web scraping process takes some time as well.

??? question "Achievement isn't given when it is supposed to?"
    First, ensure that this isnt a bug with the game itself. The game can be broken with achievements and I have no way to fix that. If that is not the case, and you notice that the file is actually changing, this is a bug and needs to be actually reported to the developer with github issues.
