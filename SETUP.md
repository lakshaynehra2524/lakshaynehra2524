# Deploying this profile

This folder is self-contained — everything needed for the GitHub profile README lives here:

```
profile/
├── profile.md                       → your profile README content
├── SETUP.md                         → this file
└── .github/workflows/snake.yml      → generates the animated contribution snake
```

## 1. Create the special profile repo

On GitHub, create a **new public repo named exactly `lakshaynehra2524`** (must match your username). GitHub auto-detects this and shows its README on your profile page.

## 2. Push these files into it

From this `profile/` folder, initialize it as that repo and push — renaming `profile.md` to `README.md` (GitHub only renders `README.md` on the profile page):

```bash
cd profile
git init
git add .
git mv profile.md README.md
git commit -m "Initial profile setup"
git branch -M main
git remote add origin https://github.com/lakshaynehra2524/lakshaynehra2524.git
git push -u origin main
```

## 3. Allow the snake Action to push

The `snake.yml` workflow commits generated SVGs to an `output` branch, so it needs write access:

1. Repo → **Settings → Actions → General → Workflow permissions**
2. Select **"Read and write permissions"** → Save

## 4. Run it once

Repo → **Actions** tab → select **"Generate Snake Animation"** → **Run workflow**. After it finishes, an `output` branch appears with the SVGs — the snake in your README will render from then on, and refreshes daily via the cron schedule.

## 5. (Optional) Fill in the second featured project

In `README.md`, find `REPLACE_WITH_REPO_NAME` under **Featured Projects** and swap in the second repo you want pinned.
