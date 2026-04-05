---
icon: fontawesome/brands/steam
---

# Steam Web API (API Key)

Using the official Steam Web API is the fastest and most reliable way to fetch accurate achievement names, global stats, and high-quality game banners. To use this method, you will need to provide your own **Steam Web API Key**.

---

## How to Get a Steam API Key

Generating an API key is completely free and only takes a minute (it does require a verified steam account).

1. Go to the [Steam Developer API Key page](https://steamcommunity.com/dev/apikey) and log in to your Steam account.
2. Under **Domain Name**, you can enter anything (e.g., localhost or RevoltUltimate).
3. Agree to the Steam Web API Terms of Use.
4. Click **Register**.
5. You will be given a long string of letters and numbers (e.g., 123ABC456DEF789GHI). **Copy this key.**

---

## How to Enter the API Key in RevoltUltimate

Once you have your key, you need to tell the app to use it:

1. Open RevoltUltimate and go to **Settings**.
2. Navigate to the **Accounts** press the plus button, and select **Steam (API Key)**
3. Find the text box labeled **Steam Web API Key**.
4. Paste the 32-character key you copied earlier into the box.
5. Paste the steamid of your profile that you can get from going to your steam profile and looking for the numbers in your url.
6. Save your settings.

RevoltUltimate will now prioritize using the official API to gather data.

---

## Troubleshooting & Warnings

??? question "Error: Unauthorized or Invalid Key"
    If you get errors saying the key is forbidden or rejected:
    **Fix:** Double-check that you copied the *entire* key without any spaces at the beginning or end.

??? warning "Missing Data or achievements not coming fast enough"
    Unfortuantely, due to steam API issues that I cannot control, if you just get an achievement it will take around 30-60 seconds for it to actual appear on the api and appear on RevoltUltimate. This is unavoiddable.

!!! danger "Security Warning"
    **Never share your API Key!** Your Web API key acts as a password for third-party apps accessing Steam on your behalf. Do not post it in screenshots, GitHub issues, or public discord servers.
