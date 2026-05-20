# Publishing to GitHub (Kbooher2) — review URL for Cris & Meredith

Goal: get this site onto your GitHub account at `github.com/Kbooher2/bbhealthtech-website` and live at a shareable preview URL on GitHub Pages — `https://kbooher2.github.io/bbhealthtech-website/`.

I tried to set up the local git repo automatically, but the `website-v1` folder lives inside OneDrive and OneDrive's sync daemon locks files in a way that prevents `git init` from working reliably. **You'll see a `.git` folder in the website-v1 directory** that got partially created — delete it before uploading (instructions below).

## The 5-minute path: GitHub web upload

This skips the terminal entirely.

### Step 1 — Delete the broken `.git` folder

In File Explorer, open `…\website-v1\`. There's a hidden `.git` folder I couldn't fully remove because OneDrive had files locked. To see it: View → Show → Hidden items. Right-click `.git` → Delete. If Windows complains, pause OneDrive sync (right-click OneDrive tray icon → Pause syncing → 2 hours), delete, then resume.

### Step 2 — Create the GitHub repo

1. Go to **https://github.com/new** (while signed in as Kbooher2)
2. Repository name: **`bbhealthtech-website`**
3. Description: *Static replacement for bbhealthtech.com — v1.0*
4. **Public** is recommended (GitHub Pages on private repos requires a paid plan, and this is marketing content anyway)
5. Leave "Add a README" UNCHECKED — we have our own
6. Leave .gitignore and license set to "None" — we have our own
7. Click **Create repository**

### Step 3 — Upload the files

On the empty repo page, click the **"uploading an existing file"** link (it's a hyperlink in the gray box near the top of the page).

1. Open `…\website-v1\` in File Explorer in another window
2. Select all files (Ctrl+A) — including the hidden `.gitignore` (View → Show → Hidden items first)
3. Drag them into the GitHub drop zone
4. Scroll down, leave the commit message as default or write "v1.0.0 — initial site"
5. Click **Commit changes**

GitHub may take 10–30 seconds to process. Done. The repo now lives at:
> `https://github.com/Kbooher2/bbhealthtech-website`

### Step 4 — Enable GitHub Pages (for the shareable preview URL)

1. In the repo, click **Settings** (top-right tab)
2. In the left sidebar, click **Pages**
3. Under "Build and deployment":
   - Source: **Deploy from a branch**
   - Branch: **`main`**, folder: **`/ (root)`**
4. Click **Save**

GitHub builds the site in 1–2 minutes. Refresh the Pages settings page and you'll see:
> *Your site is live at* **`https://kbooher2.github.io/bbhealthtech-website/`**

Send that URL to Cris and Meredith.

## Alternative: GitHub Desktop (if you'd rather use a real git workflow)

If you'd prefer to use GitHub as actual source control going forward (recommended once we get past v1.0), install **GitHub Desktop** from https://desktop.github.com.

1. File → New repository → choose `…\website-v1\` as the local path → Create
2. Publish repository (top-right button) → uncheck "Keep this code private" if you want Pages → Publish
3. Done. From here, every change you save will sync to GitHub with a click.

This works around the OneDrive lock issue because GitHub Desktop handles git operations differently than the CLI.

> **Recommended:** for ongoing maintenance, eventually move `website-v1` (or a clone of the repo) out of OneDrive — something like `C:\Users\kbooh\Code\bbhealthtech-website\`. OneDrive and git fight forever; better to keep code outside the sync zone and let GitHub be your sync mechanism.

## What to share

After Step 4, the URL to send Cris and Meredith is:

```
https://kbooher2.github.io/bbhealthtech-website/
```

It'll show the homepage. They can navigate to Platform, Company, Contact, Privacy from the top nav. The contact form uses `mailto:` so any submission would open their email client — that's expected for v1.0 review, gets swapped to a real handler before public launch.

## After review

When you have edits from Cris/Meredith, send them my way and I'll cut a v1.1 that you can re-upload (or commit via GitHub Desktop). The Pages URL updates automatically within a minute.
