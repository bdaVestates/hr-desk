# Vestates HR Desk

An installable web app for the group HR dashboard. It shows headcount, salary cost, exits, gender, and contract and probation status, all built from the Database sheet of `VESTATES_EMPLOYEE_DATABASE.xlsx`.

The app has **no staff data in it**. Each user opens the Excel file inside the app, and the file is read on their own device only. That makes it safe to host in a public GitHub repository.

## What's in this folder

| File | Purpose |
|---|---|
| `index.html` | The app |
| `manifest.webmanifest` | Name, icon and settings that make it installable |
| `sw.js` | Lets it open and work offline after the first visit |
| `icons/` | App icons |

## Put it online with GitHub Pages (about 5 minutes)

1. Go to github.com, click **New repository**, name it `hr-desk`, set it to **Public** and click **Create repository**.
2. On the new repository page, click **uploading an existing file**. Drag in `index.html`, `manifest.webmanifest`, `sw.js`, `README.md` and the whole `icons` folder, then click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, and click **Save**.
4. Wait a minute or two, then refresh the page. GitHub shows the address: `https://YOUR-USERNAME.github.io/hr-desk/`

## Install it

- **Windows or Mac (Chrome or Edge):** open the address and click **Install app** in the app's header, or the install icon at the right of the address bar. HR Desk then opens in its own window and appears in the Start menu or Applications. Once installed on a desktop, you can also right-click an `.xlsx` file and choose **Open with → HR Desk**.
- **Android (Chrome):** open the address, then go to menu ⋮ → **Install app** (or **Add to Home screen**).
- **iPhone (Safari):** open the address, then go to Share → **Add to Home Screen**.

Send the same address to anyone in HR or management who should use it. They'll also need the latest employee database file.

## Weekly use

Update the Database sheet in Excel as usual and save it. Then open HR Desk and click **Open employee file** (or drag the file onto the app). Tick **Remember file on this device** if you want it to reopen with the last file loaded.

## Updating the app later

1. Upload the new `index.html` to the repository and replace the old one.
2. Open `sw.js` on GitHub, change `const VERSION = 'hrdesk-v1';` to `'hrdesk-v2'` (then v3, and so on), and commit.

Installed copies pick up the new version the next time they're opened while online.
