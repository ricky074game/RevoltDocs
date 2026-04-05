---
icon: material/bookshelf
---

# Contributing GOG Games

If a GOG game is missing from RevoltUltimate, you will need to generate a small data file (a `.json` file) for it. Because GOG's system is a bit stricter than Steam's, you cannot generate this file directly inside RevoltUltimate.

Instead, we built a very simple tool called **[GOGAchievementFetch](https://github.com/ricky074game/GOGAchievementFetch)** that does all the hard work for you. It automatically downloads the achievement pictures and text straight from GOG's servers!

---

## Step 1: Set up GOGAchievementFetch

1. Go to the [GOGAchievementFetch Downloads Page](https://github.com/ricky074game/GOGAchievementFetch/releases).
2. Download the latest `.zip` file under "Assets".
3. Right-click the `.zip` file you downloaded and click **Extract All**, then put the folder somewhere on your computer (like your Desktop).
4. Inside that new folder, look for a file called `GOGAchievementFetch.exe`. Don't double-click it just yet! First, you need to grab two secret "keys" from your GOG account so the tool is allowed to look at your games.

*(Important: Your GOG profile's privacy settings for "Gameplay Data" MUST be set to Public on GOG.com, otherwise the tool cannot read your game list!)*

### How to get your GOG Access Tokens

We need two things from your GOG account: your `User ID` and your `Access Token`. To get them:

1. Open your web browser and log into [GOG.com](https://www.gog.com/).
2. Once logged in, open a new tab and go to this exact address: `https://embed.gog.com/userData.json`
3. You will see a messy block of text. Look carefully near the top for a number labeled `"userId":`. That is your **GOG User ID**.
4. Next, we need your Access Token. Go to this address: `https://auth.gog.com/auth?client_id=46899977096215655&redirect_uri=https%3A%2F%2Fembed.gog.com%2Fon_login_success%3Forigin%3Dhttps%3A%2F%2Fwww.gog.com&response_type=token&layout=default` and login to gog. (This is a offical link so your gog account will not get hacked)
5. Look at the web address bar at the very top of your browser. The link will have changed and will now contain a long string of letters and numbers after `access_token=`.
6. Copy that long string of letters and numbers (stop copying when you hit the `&` symbol). That is your **GOG Access Token**!

---

## Step 2: Run the Tool to Generate Your File

Now that you have your two keys, you can generate the file!

1. Go back to your extracted folder and double-click `GOGAchievementFetch.exe`.
2. A black text window will pop up saying: `Please enter your GOG User ID:`.
3. Paste or type your **User ID** number and press Enter.
4. It will then say: `Please enter your GOG OAuth Access Token:`.
5. Paste your long **Access Token** and press Enter.

The tool will now magically connect to GOG and scan for your games. When it finishes, look inside the folder where `GOGAchievementFetch.exe` is located.

You will see a brand new folder called `Achievements\GOG\`. Inside that folder will be the `.json` files you just generated (they will have long number names like `54330733943850727.json`).

---

## Step 3: Upload Your File to GitHub

Now that the tool has created the file on your computer, you need to send it to us using GitHub.

If you have never used GitHub before, **STOP HERE** and go read the [Main Contribution Guide](RevoltAchievement.md).

That guide will teach you exactly how to "Fork" our folder (make your own copy), upload your new `.json` file into the `Achievements/GOG/` folder on your copy, and send us a "Pull Request" so we can approve it!

Once an admin clicks "Approve", your file is permanently added to the global database!
