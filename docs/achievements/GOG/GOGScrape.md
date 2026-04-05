---

description: GOG Scrape achievements and features

icon: material/gog

---



# GOG Scrape (Login)

Similar to Steam Scrape, **GOG Scrape** is a feature powered by the that allows you to fetch full achievement metadata (such as rich icons, localized names, and detailed descriptions) directly from GOG's official API (`embed.gog.com`).

To gather this data accurately for your library, you need to link your GOG Account with RevoltUltimate.

---

## How to Link Your GOG Account

1. Open the **Settings** in RevoltUltimate.

2. Navigate to the **Accounts** section, and click the plus button.

3. Select **GOG Galaxy**

4. Log into your GOG account securely.

5. Once logged in, the window will automatically close. RevoltUltimate intercepts the resulting OAuth Token and saves it to pull your achievement data locally!

---

## Troubleshooting & Warnings

??? question "Failed to retrieve GOG user data"

    If the login goes through but the account fails to link, your session might be expired, or GOG's API might be having temporary issues.

    **Fix:** Click the trash icon next to your GOG account (if one was populated) and attempt the login again to get a fresh `access_token`.

??? question "Is my GOG password safe?"

    **Yes.** RevoltUltimate uses an embedded browser window that connects directly to `auth.gog.com`. The application never sees, logs, or stores your password; it only extracts the OAuth authorization code after you successfully sign in to use for read-only achievement fetching.
