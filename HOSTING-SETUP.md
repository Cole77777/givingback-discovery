# One site for Privacy + Support (GitHub Pages)

**Your repo name (use this on GitHub):** `givingback-discovery`  
**Your GitHub user:** `Cole77777`  
**Your live site (after Pages is on):** `https://cole77777.github.io/givingback-discovery/`  
*(GitHub shows the `github.io` host in lowercase; that’s normal.)*

Use **that same `https://…github.io/…/` URL** in App Store Connect for **Privacy Policy URL** and **Support URL**.

`docs/index.html` is already filled with your email and GitHub links.

---

## Step A — Create the repository

1. Go to **https://github.com** and sign in as **Cole77777**.
2. **+** → **New repository**.
3. **Repository name:** type exactly **`givingback-discovery`** (all lowercase, hyphen).
4. **Public** → **Create repository**.

---

## Step B — Add the `docs` folder to `main`

### About `.nojekyll` (easy to “not see”)

The second file is **`.nojekyll`** (starts with a **dot**). It tells GitHub Pages **not** to run Jekyll on your HTML. The file is **empty** and **zero bytes**—that’s correct.

- **In Cursor / VS Code:** Explorer often **hides dotfiles**. Open the folder `docs` and use **File → Open File…** and pick `.nojekyll`, or in Terminal run `ls -la docs` — you should see it next to `index.html`.
- **In Finder:** Press **`⌘⇧.`** (Command–Shift–period) to **show hidden files**, then open `The Donor` → `docs` → **`.nojekyll`**.
- **On GitHub in the browser:** “Add file” → name the path **`docs/.nojekyll`** — GitHub allows dot names even if your computer hides them locally.

### Option 1 — Upload in the browser

1. On the empty repo, click **uploading an existing file**.
2. Add **`docs/index.html`** from your Mac: in the “name your file” box use **`docs/index.html`** (include the `docs/` prefix).
3. Add **`docs/.nojekyll`** the same way (create a second file, name **`docs/.nojekyll`** — leave the file **completely empty**).
4. Commit to **`main`**.

### Option 2 — Push from your Mac

```bash
cd "/Users/colemilstein/The Donor"
git init
git remote add origin https://github.com/Cole77777/givingback-discovery.git
git add docs/index.html docs/.nojekyll docs/HOSTING-SETUP.md
git commit -m "Add GitHub Pages (privacy + support)"
git branch -M main
git push -u origin main
```

If `remote already exists`, use `git remote set-url origin https://github.com/Cole77777/givingback-discovery.git`.

---

## Step C — Enable GitHub Pages

1. Repo **Settings** → **Pages**.
2. **Source:** **Deploy from a branch**.
3. **Branch:** `main` → **Folder:** **`/docs`** → **Save**.
4. Wait until the banner shows the site URL (often **1–3 minutes**).

---

## Step D — App Store Connect

Paste this for **both** Privacy Policy URL and Support URL:

```text
https://cole77777.github.io/givingback-discovery/
```

Optional **Marketing URL**:

```text
https://github.com/Cole77777/givingback-discovery
```

---

## Troubleshooting

### Error: Jekyll / `No such file or directory … /github/workspace/docs`

That log means GitHub tried to **build with Jekyll** and **could not find a `docs` folder** in the copy of your repo on GitHub.

**Do this first (on github.com → your repo → Code):**  
Check that you see a folder **`docs`** with **`index.html`** inside. If **`docs` is missing**, the fix is only on your Mac: commit the whole **`The Donor/docs`** folder, push to **`main`**, then re-run the workflow or wait for Pages to rebuild.

**Then pick ONE way to publish Pages (avoid mixing):**

**Option A — Simplest (recommended)**  
1. Repo **Settings** → **Pages**.  
2. **Build and deployment** → **Source:** **Deploy from a branch** (not “GitHub Actions”).  
3. **Branch:** `main`, **Folder:** **`/docs`** → Save.  
4. If GitHub added a **Jekyll** workflow under **Actions** that you don’t want, delete any extra workflow under **.github/workflows/** that mentions Jekyll / `github-pages` (keep **`deploy-static-pages.yml`** only if you switch to Option B).

**Option B — GitHub Actions (static, no Jekyll)**  
1. This project includes **`.github/workflows/deploy-static-pages.yml`**, which uploads **`docs/`** as static files only.  
2. **Settings** → **Pages** → **Source:** **GitHub Actions**.  
3. Delete any **other** Pages workflow GitHub suggested (often Jekyll-based) so only **`deploy-static-pages.yml`** runs.  
4. Ensure **`docs/`** is on **`main`** (same as above), then push a commit or **Actions** → **Deploy static Pages** → **Run workflow**.

---

- **404:** Confirm Pages uses **`main`** + **`/docs`** (or Actions deploy) and **`docs/index.html`** exists on **`main`**.
- **Repo name typo:** The repo **must** be named **`givingback-discovery`** for the links in `index.html` to match the Issues URL.
