# Fast Travel

**Supercharge your search bar**

Fast Travel is a Bunnylol-inspired, configurable, command-based search engine replacement that you can easily host on GitHub Pages. It lets you streamline your searches and navigate the web quickly with a lightweight, static engine designed for speed and simplicity.

For example:

- Typing `g kittens` will search for "kittens" on Google.
- Typing `ddg privacy` will search for "privacy" on DuckDuckGo.
- Typing `r r/technology` will take you directly to the r/technology subreddit.
- Typing `hn` will take you directly to Hacker News.
- Typing `apps balatro` will search for "balatro" on Steam on desktop, the Google Play Store on Android, and the App Store on iOS.

Fast Travel works similarly to search bangs—but without the need for an exclamation mark—and it’s highly customizable.

## Setup Instructions

1. **Fork the Repository:**  
   Click the "Fork" button on the repository page to create your own copy.

2. **Deploy on GitHub Pages:**  
   - Update the page URL in your repository settings (navigate to `Settings > Pages > Custom domain`) or configure the `CNAME` file.
   - It is recommended to use a subdomain (e.g., `fast-travel.yourdomain.com`) or a root domain (e.g., `yourdomain.com`) rather than deploying on a subdirectory (e.g., `yourdomain.com/fast-travel`), as not all platforms correctly recognize subdirectory URLs for search engines.

3. **Optional – Enable GitHub Actions:**  
   If you experience workflow failures, consider enabling GitHub Actions with write access to ensure necessary updates are applied.

4. **Optional – Update Your Config:**  
   Open the `config.json` file to modify, add, or remove commands and routes.

5. **Replace Your Search Engine:**  
   Follow these steps to replace your default search engine in popular browsers:

    <details>
    <summary><strong>Chrome on Windows/MacOS</strong></summary>

    1. Open **Settings > Search Engine > Manage search engines** or paste `chrome://settings/searchEngines` into your address bar.
    2. In the "Site search" (or "Other search engines") section, click **Add**.
    3. Fill in the details:
    - **Search engine:** Fast Travel
    - **Shortcut:** (e.g., `ft`)
    - **URL:** `https://fast-travel.yourdomain.com?q=%s`
    4. Click **Add**.
    5. Next to your new entry, click the menu icon and select **Make default**.
    </details>

    <details>
    <summary><strong>Chrome on Android/iOS</strong></summary>

    1. Visit your Fast Travel page (e.g., `https://fast-travel.yourdomain.com`).
    2. Perform a search using Fast Travel. (Don't skip this step.)
    3. Tap the three dots in the top-right corner.
    4. Choose **Settings**, then **Search engine**.
    5. Select **Fast Travel** from the "Recently visited" section.
    </details>

    <details>
    <summary><strong>Firefox on Windows/MacOS</strong></summary>

    1. Visit your Fast Travel page (e.g., `https://fast-travel.yourdomain.com`).
    2. Right-click on the address bar and choose **Add Fast Travel**.
    3. Open the hamburger menu in the top-right corner, then go to **Settings > Search**.
    4. In the "Default Search Engine" section, select **Fast Travel** from the drop-down menu.
    </details>

    <details>
    <summary><strong>Firefox on Android/iOS</strong></summary>

    1. Tap the three dots in the top-right corner.
    2. Choose **Settings**, then **Search**.
    3. Select **Default Search Engine**, then **+ Add Search Engine**
    4. Fill in the details:
    - **Name:** Fast Travel
    - **Search string URL:** `https://fast-travel.yourdomain.com?q=%s`
    5. Select Fast Travel
    </details>

    **Note:**  
     Using a custom domain (like `fast-travel.yourdomain.com` or `yourdomain.com`) is preferred over a subdirectory deployment for optimal compatibility.

## How the Commands Work

Fast Travel uses a command-based syntax defined in the `config.json` file. Commands are processed sequentially—if a query matches multiple patterns, the first match is used. Here’s how to use and customize them:

### Basic Command Usage

- **Open the Page:**  
  - **Syntax:** `<command>`  
  - **Example:** Typing `g` opens the default Google homepage.

- **Search a Query:**  
  - **Syntax:** `<command> <query>`  
  - **Example:** Typing `g kittens` searches for "kittens" on Google using the command's fallback URL.

- **Subcommands / Custom Patterns:**  
  - **Syntax:** `<command> <subcommand>/<query>` or using a custom regex defined in the config.  
  - **Examples:**  
    - Typing `yt subs` opens your YouTube subscriptions.
    - Typing `r r/asksf` takes you directly to the r/asksf subreddit.

### OS-Specific Options

Fast Travel adjusts its behavior based on your device’s operating system. The `config.json` file includes routes optimized for various platforms:

- **Desktop:** Windows, MacOS, Linux
- **Mobile:** Android, iOS
- **Fallback:** Use `*` to apply to all devices

For instance, the `apps` command provides different routing options depending on whether you’re on Android (using the Play Store), iOS (using the App Store), or Desktop (using the Steam Store).

### Customizing Commands

- **Editing the Config:**  
  Open the `config.json` file to modify, add, or remove commands and their routes. You can customize:
  - **Default URLs:** The page that opens when no query is provided.
  - **Fallback URLs:** Used for searches by appending the query to a specified URL.
  - **Custom Patterns:** Regex or pattern-based routing (e.g., `r r/asksf`) for advanced operations. These patterns typically follow the `subcommand/<parameter>` structure.

- **Order of Processing:**  
  The file is parsed sequentially. If a query matches multiple patterns, the first match is used. Arrange your custom patterns accordingly to ensure the desired behavior.

## Credits

### Ten Blue Links

Thanks to [Ten Blue Links](https://tenbluelinks.org/) for serving as a valuable reference on how to replace the default search engine.

### Favicon

This favicon was generated using graphics from Twitter Twemoji:

- **Author:** Copyright 2020 Twitter, Inc and other contributors ([GitHub Repository](https://github.com/twitter/twemoji))
- **Source:** [1f50e.svg](https://github.com/twitter/twemoji/blob/master/assets/svg/1f50e.svg)
- **License:** [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)
