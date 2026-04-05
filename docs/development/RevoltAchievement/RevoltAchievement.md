---
icon: material/bookshelf
---

# Revolt Achievement Library

The **RevoltAchievement** repository is the central database that powers the offline achievement tracking of RevoltUltimate. It contains hundreds of .json files representing different games for various platforms (Steam & GOG).

Whenever you open a game in RevoltUltimate, it checks this repository to fetch the correct names, descriptions, and icons for the achievements. If a game you play is missing, returning "Unknown Achievement" or blank icons, you can contribute to the database without needing any coding knowledge!

---

## How the System Works

The repository is structured quite simply. Inside the [RevoltAchievement](https://github.com/ricky074game/RevoltAchievement) GitHub repository, there is an \Achievements\ folder containing subfolders for each platform:

- \Achievements/Steam/\ *(Contains files like \123456.json\)*
- \Achievements/GOG/\ *(Contains files like \123456789.json\)*

To contribute a missing game, your goal is to simply generate this JSON file using our tools and upload it to GitHub via a Pull Request (PR).

---

## How to Contribute

Don't worry, you don't need to be a developer to contribute. The general process applies to all platforms:

1. **Generate the File:** First, use one of our automated tools to generate the \.json\ file for your game.
2. **Go to GitHub:** Navigate to the [RevoltAchievement Repository](https://github.com/ricky074game/RevoltAchievement).
3. **Upload the File:** Add your generated file to the proper directory (\Achievements/Platform/\).
4. **Submit a Pull Request:** GitHub will guide you through submitting a Pull Request. Once approved, your game will be permanently added to RevoltUltimate for everyone!

To learn exactly how to generate the files for your specific platform, choose one of the detailed guides below:

- [GOG Contributions](RevoltGOG.md)
