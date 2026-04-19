# GitHub Pages — **root** `index.html` only (no `docs/` folder)

GitHub Pages can publish from the **root of `main`**. Then you only upload **`index.html`** (and one tiny helper file) at the **top level** of the repo — **not** inside a `docs/` folder.

**Why it “didn’t work” with only `index.html` before:**  
Your site was set to **Build from `/docs`**. GitHub then looks for **`docs/index.html`**. A file named **`index.html` sitting at the repo root** is **ignored** for that setting.

**Fix:** Change Pages to **root** (below). Then your root **`index.html`** is the homepage.

---

## Files (in your Mac project `The Donor/`)

| File | Where it goes on GitHub |
|------|-------------------------|
| **`index.html`** | **Root** of the repo (same level as README) |
| **`.nojekyll`** | **Root** of the repo — **empty file**, stops Jekyll |

Your Mac already has both at **`The Donor/index.html`** and **`The Donor/.nojekyll`**.

---

## Step 1 — GitHub repo

Use any public repo (e.g. **`givingback-discovery`**). It can contain only these two files plus a README if you want.

---

## Step 2 — Upload **only** to the **root**

1. On GitHub: **Add file** → **Upload files**.
2. Drag **`index.html`** from **`The Donor/`** — it must appear as **`index.html`** at the **root** (not `docs/index.html`).
3. Add **`.nojekyll`**: **Add file** → **Create new file** → filename **`.nojekyll`** → leave blank → **Commit**.  
   *(In Finder, show hidden files with **⌘⇧.** to see `.nojekyll` on your Mac.)*

---

## Step 3 — GitHub Pages settings (this is the important part)

1. Repo **Settings** → **Pages**.
2. **Build and deployment** → **Source:** **Deploy from a branch**.
3. **Branch:** `main` → folder **`/ (root)`** — **not** `/docs`.
4. **Save**.

---

## Step 4 — Your live URL

After a minute or two:

```text
https://cole77777.github.io/REPO_NAME/
```

Replace **`REPO_NAME`** with your real repository name (e.g. `givingback-discovery`).

Use **that URL** for **Privacy Policy URL** and **Support URL** in App Store Connect (same link is fine).

---

## Edit the Issues link (optional)

Open **`index.html`** on GitHub and change the GitHub Issues URL if your repo name isn’t `givingback-discovery`.
