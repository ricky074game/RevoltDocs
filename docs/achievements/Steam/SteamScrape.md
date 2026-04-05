---
icon: fontawesome/brands/steam
---

# Steam Scrape (Login)

Steam Scrape is a feature in RevoltUltimate that allows you to fetch rich achievement data (like high-quality icons, detailed descriptions, and global unlock percentages) directly from Steam without needing an API key.

Instead of an API key, this method requires you to log in to Steam through the application so it can browse the store and community pages on your behalf.

---

## How to Set Up Steam Scrape

1. Open RevoltUltimate and navigate to the **Settings** or **Accounts** page.
2. Locate the **Accounts** section, press the plus button and select **Steam (Web Login)**
3. A built-in Steam Login window will appear. Enter your Steam credentials.
4. If you have Steam Guard (2FA) enabled, enter the code from your mobile app or email.
5. Once logged in, the window will close, and RevoltUltimate will save a secure session cookie to use for scraping.

---

## Troubleshooting & Common Errors

If you are having issues scraping data using your logged-in account, check the following common problems:

??? failure "Error: Profile is Private"
    If your Steam profile privacy settings restrict your game details, the scraper might fail to see your game library or achievements.
    **Fix:** Go to your Steam Profile -> Edit Profile -> Privacy Settings. Ensure your **Game details** are set to **Public** while using the scraper.

??? failure "Error: Session Expired or Not Logged In"
    Steam session cookies expire over time or when you change your password.        
    **Fix:** Simply go back to the Accounts/Settings page in RevoltUltimate and log in again to refresh your session.

??? failure "Endless Loading or Captcha Loops"
    Sometimes the built-in browser window can get stuck on a captcha or loading screen.
    **Fix:** Close the login window and try again. If it persists, ensure you don't have network configurations (like VPNs or strict firewalls) blocking Steam community sites.

??? info "Is my password safe?"
    **Yes.** RevoltUltimate uses an embedded browser window (WebView) that logs directly into Steam's official website. The app never sees your password; it only extracts the resulting session cookie (SerializableCookie.cs behind the scenes) to fetch store pages.
