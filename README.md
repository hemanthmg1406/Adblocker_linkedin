# LinkedIn Ad Blocker Extension

## 📘 **Project Overview**
The **LinkedIn Ad Blocker** is a browser extension designed to remove advertisements from the LinkedIn feed, providing a cleaner, distraction-free browsing experience. This extension automatically detects and hides LinkedIn ads labeled as "Promoted" using simple, efficient logic.

## 📂 **Project Structure**
```
📦 LinkedIn Ad Blocker
 ┣ 📜 extension.js  -- Handles background logic and URL detection
 ┣ 📜 linkedin.js   -- Core script to remove ads from the LinkedIn feed
 ┗ 📜 manifest.json -- Extension configuration file
```

### **1. `manifest.json`**
The `manifest.json` file defines the extension's essential metadata and permissions. Key highlights include:
- **manifest_version**: Specifies version 2 of the extension system.
- **name**: The name of the extension ("LinkedIn Ad-Blocker").
- **version**: Version 0.0.1.
- **permissions**: Grants the extension access to tabs, web navigation, and LinkedIn URLs.
- **background**: Specifies `extension.js` as the background script.

---

### **2. `extension.js`**
The `extension.js` file is responsible for detecting when the user navigates to LinkedIn and triggering the ad removal process. Key functionalities include:
- **URL Detection**: Listens for URL changes using `chrome.webNavigation.onCommitted`.
- **LinkedIn URL Check**: Verifies if the current tab URL contains "linkedin.com".
- **Script Injection**: If LinkedIn is detected, it injects and runs the `linkedin.js` file to remove ads.

### **3. `linkedin.js`**
This file contains the logic to identify and hide LinkedIn ads. Key steps include:
- **Ad Detection**: Identifies LinkedIn ads by checking if any `<span>` elements contain the text "Promoted".
- **Ad Removal**: Locates the ad's parent container and hides it using `style.display = 'none'`.
- **Auto-Update**: Uses `setInterval()` to ensure that newly loaded ads as the user scrolls are also hidden.

## 📦 **Installation Instructions**
Follow the steps below to install and use the **LinkedIn Ad Blocker**.

1. **Download the Source Code**
   - Download or clone the project files (`manifest.json`, `extension.js`, `linkedin.js`).

2. **Enable Developer Mode**
   - Open Google Chrome and navigate to `chrome://extensions/`.
   - Enable **Developer Mode** (toggle in the top-right corner).

3. **Load Unpacked Extension**
   - Click on **Load unpacked**.
   - Select the folder containing `manifest.json`, `extension.js`, and `linkedin.js`.

4. **Verify Installation**
   - Once loaded, the extension will appear in the Chrome extensions bar with the name **LinkedIn Ad-Blocker**.

5. **Enjoy Ad-Free LinkedIn!**
   - Navigate to LinkedIn, and you will no longer see "Promoted" ads in your feed.

---

## ⚙️ **How It Works**
1. **URL Detection**: When you visit a page, the extension checks if the URL contains `linkedin.com`.
2. **Script Injection**: If LinkedIn is detected, the `linkedin.js` script is injected into the page.
3. **Ad Removal**: The script scans for any ad labels ("Promoted") and removes the corresponding containers from the feed.

---

## 🛠️ **Technologies Used**
- **JavaScript**: Core scripting language used in the extension logic.
- **Chrome Extensions API**: Used for tab navigation, content script injection, and background processes.

---

## 🌟 **Features**
- **Ad Blocking**: Removes all "Promoted" posts from the LinkedIn feed.
- **Real-Time Ad Removal**: As the user scrolls, new ads are automatically detected and removed.
- **Lightweight & Fast**: Efficient ad removal with minimal performance impact.

---

## 🔥 **Possible Improvements**
- **Dynamic Ad Label Detection**: Some ads may be labeled with text other than "Promoted". Future versions could use more robust pattern matching.
- **More Efficient DOM Traversal**: The current script climbs the DOM hierarchy to locate ad containers. It could be optimized using more efficient traversal methods.
- **Customization**: Add an options page where users can specify keywords or content types to block.

---

## 👨‍💻 **Author**
- **Hemanthkumar**
- Version: 0.0.1

If you have any questions or suggestions,ping me.

