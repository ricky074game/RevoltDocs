---

description: Comet Offline achievements and features

icon: material/gog

---



# CometOffline

**CometOffline** is a custom built-in Rust emulator module integrated directly into RevoltUltimate that completely bypasses the need for putting proxy `.dll` files in your game directory.

Instead of reading achievement files, it hosts a local backend server (listening on `127.0.0.1:3333`) and strategically redirects the official GOG domain traffic on your computer directly into RevoltUltimate! This allows untouched GOG games to track natively.

---

## How to Configure and Start the Comet Server

1. Open the **Settings** in RevoltUltimate.

2. Go to the **Comet** options page.

3. You will see an interface managing the local Comet server. Make sure the Server Status is running.

4. Click the button to **Install Hosts Patch**. 

    - *Note: This requires Windows Administrator privileges to modify `C:\Windows\System32\drivers\etc\hosts`.*

5. This will securely point `auth.gog.com`, `users.gog.com`, and `presence.gog.com` to `localhost`.

6. Launch your GOG game! You do not need to add the game folder. RevoltUltimate will automatically intercept the traffic and pop achievements.

---

## Important Notes & Troubleshooting

??? question "Why does normal GOG Galaxy stop working?"

    As long as the "Hosts Patch" is active, your official GOG Galaxy client will be unable to connect to the internet, because all network traffic is being redirected to RevoltUltimate!

    **Fix:** When you are done playing offline games, return to the **Comet Options** page and click **Uninstall Hosts Patch** to restore normal internet access for GOG.

??? question "Why does the server say \"Executable not found\"?"

    If RevoltUltimate gives you an error saying `comet.exe` is missing from the directory, your antivirus may have deleted it, or you may be running a source build and forgot to compile the `cometOffline` rust submodule.

    **Fix:** If using a pre-compiled release, reinstall the application and whitelist it in Windows Defender. If building from source, make sure you run `cargo build --release` in the `cometOffline` folder.

??? question "Why doesn't my game appear in RevoltUltimate?"

    First ensure the game actually uses GOG Achievements (not that many do), even if they have achievements on Steam. If that doesn't work. Please follow these instructions: <https://github.com/imLinguin/comet/blob/main/dummy-service/README.md>.

??? question "Why does my game show up with 0/0 achievements?"

    Unfortunately, due to how GOG works, the game nor the GOG servers do not report the achievements and the only way to fetch it if a user that has bought the game can report it. These files are not created yet. You would either need to provide it yourself (you need to own the game in GOG), or ask someone else to provide them for you. You can ask for this request here (github account required): <https://github.com/ricky074game/RevoltAchievement>
